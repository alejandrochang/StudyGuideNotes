# Redux

### What is Redux
A state management library, makes creating complex apps a little bit easier.

### What is the Redux Cycle?
Action Creator -> Action -> Dispatch -> Reducers -> State

### What does the action creator do?
The action creator is a function that is going to create or return a plain JS object. 
This plain JS object is referred to as the action.

### What are the two things the Action has?
The action has a type and a payload. The type: describes some change we want to make on our data.
The payload property: describes some context around the change we want to make. 
The purpose of an action is to describe some change that we want to make inside of our application.

### What is payload in regards to Redux context?
The payload is what is bundled in your actions and passed around between reducers in your redux application.

### What does the dispatch function do?
The dispatch function takes in some action, make copies of that object and then passes it on to different places in our application. 

```js

const { createStore , combineReducers } = Redux;
const ourDepartments = combineReducers({
  accounting: accounting,
  claimsHistory: claimsHistory,
  policies: policies
});
const store = createStore(ourDepartments);

store.dispatch(createPolicy('Alex', 20));
store.dispatch(createPolicy('Nancy', 30));
store.dispatch(createClaim('Nancy', 120));
store.dispatch(deletePolicy('Bob'));
console.log(store.getState()); // { accounting: 20, claimsHistory: [{...}], policies: ["Alex", "Nancy"]}
```

### What does Reducers do?
A reducer is a function that is responsible for taking in an action and some existing amount of data. It's going to process that action, make some changes to the data and return it so then it could be centralized in some other location.
It is going to change that data based on the contents of that action.

### What does the State property in Redux do?
The state property in Redux is a central repository of all the information that has been created by our reducers. All of the information gets consolidated in our react object so that React has access to reach into the Redux part of our applciation and get the appropriate data. 

### How do you modify the state?
The only way to modify the state in your store is to dispatch and action creator to modify it. There is no way to modify it directly. 

### In reducers why do you always want to create a new array rather than modify an old one?
You always want to create a new array rather than modifying a new one. This can be done with ...rest/splat operator.

### What is the Store in Redux?
A store in redux is essentially the collection of different reducers and action creators.

### Why use Redux?
As our app becomes bigger, the complexity tends to exponentially rise. With Redux, our app might become more complex from the beginning, but as the application grows, the complexity looks more linear than exponential. 
