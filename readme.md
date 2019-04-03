# use-global-hook

Easy state manegment for react using hooks in less than 1kb.

Minimal example:
```javascript
import React from 'react';
import useGlobalHook from 'use-global-hook';

const initialState = {
  counter: 0,
};

const actions = {
  addToCounter: (store, amount) => {
    const counter = store.state.counter + amount;
    store.setState({ counter });
  },
};

const useGlobal = useGlobalHook(React, initialState, actions);

const App = () => {
  const [globalState, globalActions] = useGlobal();
  return (
    <div>
      <p>
        counter:
        {globalState.counter}
      </p>
      <button type="button" onClick={() => globalActions.addToCounter(1)}>
        +1 to global
      </button>
    </div>
  );
};

export default App;
```