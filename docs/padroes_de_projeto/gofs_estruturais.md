# GOF's Estruturais

## Histórico de Versões

|   Data   | Versão |           Descrição           |             Autor(es)              |
|:--------:|:------:|:-----------------------------:|:----------------------------------:|
| 24/10/2020 | 0.1 | Adicionado o documento | Julio Litwin |
| 26/10/2020 | 0.2 | Adicionado o padrão Flyweight | Julio Litwin |

## Introdução

Os Padrões Estruturais lidam com a composição de classes e objetos. Eles fornecem maneiras diferentes de usar composição e herança de objetos para criar alguma abstração.

## Flyweight
O Flyweight é um padrão de projeto estrutural que permite a você colocar mais objetos na quantidade de RAM disponível ao compartilhar partes comuns de estado entre os múltiplos objetos ao invés de manter todos os dados em cada objeto.

### Prós
- Você pode economizar muita RAM, desde que seu programa tenha muitos objetos similares.

### Contras
- Você pode estar trocando RAM por ciclos de CPU quando parte dos dados de contexto precisa ser recalculado cada vez que alguém chama um método flyweight.
- O código fica muito mais complicado. Novos membros de equipe sempre se perguntarão por que o estado de uma entidade foi separado de tal forma.

### Aplicabilidade
Será utlizado um "Object Pool" na parte do Front, na qual tais como na estrutura de UI, como reaproveitar um botão e apenas trocar o texto. Também será usado na questão de sons, na qual ao invés de instanciar toda vez o som, será usado a partir do Object Pool, toda vez que for ser utilizado.

Na linguagem net core, o object pool é muito útil por conta do Garbage Collection, é reduzido drasticamente as inicializações e destruições de objetos, pois estão sendo reutilizados ao invés de instanciando. 

#### Diagrama
![FlyweightDiagrama](../img/diagramas/flyweight_ui_button.png)

#### Código

**Observação**: MonoBehaviour é uma classe da própria Unity 3D.

```
public class ObjectPool : MonoBehaviour
{
    public GameObject Prefab;
    public int InitialSize;

    private readonly Stack<GameObject> instances = new Stack<GameObject>();

    private void Awake()
    {
        Assert.IsNotNull(Prefab);
    }

    private void Start()
    {
        for (var i = 0; i < InitialSize; i++)
        {
            var obj = CreateInstance();
            obj.SetActive(false);
            instances.Push(obj);
        }
    }

    public GameObject GetObject()
    {
        var obj = instances.Count > 0 ? instances.Pop() : CreateInstance();
        obj.SetActive(true);
        return obj;
    }

    public void ReturnObject(GameObject obj)
    {
        var pooledObject = obj.GetComponent<PooledObject>();
        Assert.IsNotNull(pooledObject);
        Assert.IsTrue(pooledObject.Pool == this);

        obj.SetActive(false);
        instances.Push(obj);
    }

    public void Reset()
    {
        var objectsToReturn = new List<GameObject>();
        foreach (var instance in transform.GetComponentsInChildren<PooledObject>())
        {
            if (instance.gameObject.activeSelf)
            {
                objectsToReturn.Add(instance.gameObject);
            }
        }
        foreach (var instance in objectsToReturn)
        {
            ReturnObject(instance);
        }
    }

    private GameObject CreateInstance()
    {
        var obj = Instantiate(Prefab);
        var pooledObject = obj.AddComponent<PooledObject>();
        pooledObject.Pool = this;
        obj.transform.SetParent(transform);
        return obj;
    }
}
```

O objeto na qual será reutilizado, é definido em **Prefab**. Sempre que for necessário obter o objeto, é chamado o **GetObject()**, na qual irá verificar se há disponibilidade de objeto, caso não, irá instanciar um novo objeto para ser utilizado e adicionado numa stack.

### Referências

- **Baeldung**, Proxy, Decorator, Adapter and Bridge Patterns. Disponível em: <https://www.baeldung.com/java-structural-design-patterns>. Acesso em: 24 de Setembro 2020.

- **REFACTORING . GURU**, Structural Design Patterns. Disponível em: <https://refactoring.guru/design-patterns/structural-patterns>. Acesso em: 24 de Setembro 2020.

- **TreinaWeb**, Padrões de projeto: o que são e o que resolvem. Disponível em: <https://www.treinaweb.com.br/blog/padroes-de-projeto-o-que-sao-e-o-que-resolvem/>. Acesso em: 24 de Setembro 2020.

- **Wikipedia**, Padrão de projeto de software. Disponível em: <https://pt.wikipedia.org/wiki/Padr%C3%A3o_de_projeto_de_software>. Acesso em: 24 de Setembro 2020.

- **Unity 3D**, Object Pooling. Disponível em: <https://unity3d.com/learn/tutorials/topics/scripting/object-pooling>. Acesso em: 26 de Setembro 2020.