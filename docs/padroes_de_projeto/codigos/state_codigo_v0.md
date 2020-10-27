- EnUserFSMState
```
    /// <summary>
    /// Jogador FSM State.
    /// </summary>
    public enum EnUserFSMState
    {
        STATE_ZERO_NO_USE,

        STATE_INIT = 1,
        STATE_CONNECTED = 2,
        STATE_EXIT = 3,
        STATE_LOGINING,

        STATE_CHARACTER_CREATE,
        STATE_CHANNELLOBBY,

        STATE_CHANNEL,
        STATE_ROOM,
        STATE_PLAYING,

        STATE_SENTINEL
    }
```

- EnUserFSMInput
```
    /// <summary>
    /// User FSM Input.
    /// </summary>
    public enum EnUserFSMInput
    {
        INPUT_VERIFICATION = 0,

        INPUT_VERIFICATION_FAIL,
        INPUT_VERIFICATION_OK,
        INPUT_VERIFICATION_CREATE_CHARACTER,

        INPUT_EXIT_GAME,

        INPUT_TO_CHARACTER_CREATE,

        INPUT_TO_CHANNELLOBBY,
        INPUT_TO_CHANNEL,
        INPUT_JOIN_ROOM,
        INPUT_START_GAME_OK,
        INPUT_END_GAME_OK,

        INPUT_CONNECT,
    }
```

- IJogador
```
public interface IJogador
{
    bool Ação(int id);
    void ReactNotify();
}
```

- JogadorFSM
```
public class JogadorFSM : FSMClass
    {
        /// <summary>
        /// Constructor.
        /// </summary>
        public JogadorFSM()
            : base((int)EnUserFSMState.STATE_INIT)
        {
            // STATE_INIT
            FSMState state = new FSMState((int)EnUserFSMState.STATE_INIT, 2);
            state.AddTransition((int)EnUserFSMInput.INPUT_CONNECT, (int)EnUserFSMState.STATE_CONNECTED);
            state.AddTransition((int)EnUserFSMInput.INPUT_EXIT_GAME, (int)EnUserFSMState.STATE_EXIT);
            if (AddState(state) == false)
            {
                state = null;
            }

            // STATE_CONNECTED
            state = new FSMState((int)EnUserFSMState.STATE_CONNECTED, 2);
            state.AddTransition((int)EnUserFSMInput.INPUT_VERIFICATION, (int)EnUserFSMState.STATE_LOGINING);
            state.AddTransition((int)EnUserFSMInput.INPUT_EXIT_GAME, (int)EnUserFSMState.STATE_EXIT);
            if (AddState(state) == false)
            {
                state = null;
            }

            // STATE_LOGINING
            state = new FSMState((int)EnUserFSMState.STATE_LOGINING, 3);
            state.AddTransition((int)EnUserFSMInput.INPUT_VERIFICATION_OK, (int)EnUserFSMState.STATE_CHANNELLOBBY);
            state.AddTransition((int)EnUserFSMInput.INPUT_VERIFICATION_CREATE_CHARACTER, (int)EnUserFSMState.STATE_CHARACTER_CREATE);
            state.AddTransition((int)EnUserFSMInput.INPUT_VERIFICATION_FAIL, (int)EnUserFSMState.STATE_CONNECTED);
            if (AddState(state) == false)
            {
                state = null;
            }

            // STATE_CHARACTER_CREATE
            state = new FSMState((int)EnUserFSMState.STATE_CHARACTER_CREATE, 1);
            state.AddTransition((int)EnUserFSMInput.INPUT_TO_CHARACTER_CREATE, (int)EnUserFSMState.STATE_CHANNELLOBBY);
            if (AddState(state) == false)
            {
                state = null;
            }

            // STATE_CHANNELLOBBY
            state = new FSMState((int)EnUserFSMState.STATE_CHANNELLOBBY, 3);
            state.AddTransition((int)EnUserFSMInput.INPUT_TO_CHANNEL, (int)EnUserFSMState.STATE_CHANNEL);
            state.AddTransition((int)EnUserFSMInput.INPUT_EXIT_GAME, (int)EnUserFSMState.STATE_EXIT);
            state.AddTransition((int)EnUserFSMInput.INPUT_JOIN_ROOM, (int)EnUserFSMState.STATE_ROOM);
            if (AddState(state) == false)
            {
                state = null;
            }

            // STATE_CHANNEL
            state = new FSMState((int)EnUserFSMState.STATE_CHANNEL, 2);
            state.AddTransition((int)EnUserFSMInput.INPUT_TO_CHANNELLOBBY, (int)EnUserFSMState.STATE_CHANNELLOBBY);
            state.AddTransition((int)EnUserFSMInput.INPUT_JOIN_ROOM, (int)EnUserFSMState.STATE_ROOM);
            if (AddState(state) == false)
            {
                state = null;
            }

            // STATE_ROOM
            state = new FSMState((int)EnUserFSMState.STATE_ROOM, 3);
            state.AddTransition((int)EnUserFSMInput.INPUT_TO_CHANNEL, (int)EnUserFSMState.STATE_CHANNEL);
            state.AddTransition((int)EnUserFSMInput.INPUT_START_GAME_OK, (int)EnUserFSMState.STATE_PLAYING);
            state.AddTransition((int)EnUserFSMInput.INPUT_TO_CHANNELLOBBY, (int)EnUserFSMState.STATE_CHANNELLOBBY);
            if (AddState(state) == false)
            {
                state = null;
            }

            // STATE_PLAYING
            state = new FSMState((int)EnUserFSMState.STATE_PLAYING, 2);
            state.AddTransition((int)EnUserFSMInput.INPUT_END_GAME_OK, (int)EnUserFSMState.STATE_ROOM);
            state.AddTransition((int)EnUserFSMInput.INPUT_TO_CHANNEL, (int)EnUserFSMState.STATE_CHANNEL);
            if (AddState(state) == false)
            {
                state = null;
            }

            // STATE_EXIT
            state = new FSMState((int)EnUserFSMState.STATE_EXIT, 0);
            if (AddState(state) == false)
            {
                state = null;
            }
        }
    }
```