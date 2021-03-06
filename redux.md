# Redux

### What is Redux
A state management library, makes creating complex apps a little bit easier.

### What is the Redux Cycle?
Action Creator -> Action -> Dispatch -> Middleware -> Reducers -> State

To change state in our app we call an action creator which produces an action, which gets fed to dispatch which forwards the action to middleware which sends the action to reducers and creates a new state. 

### What does the action creator do?
The action creator is a function that is going to create or return a plain JS object. 
This plain JS object is referred to as the action which must have a TYPE and optionally can have a payload.

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

The reducer takes in previous state + action.

Reducer Rules:
1. The one rule of reducers is that they cannot return undefined.
2. Produces 'state' or data using only previou state and the action.
3. Keep the reducer pure by never reaching out of the reducer.
4. Dont mutate the 'state' (first) argument in a reducer.
    -> You should worry about mutating an [] or an {}, strings and numbers are primitives( hence: immutable)
    Note: If you return the state the end of the function you're application won't update. It is only when you return a "modified" state that it updates.

### What are good operation to do on Reducer to avoid mutating state?
Removing an element from an array: state.filter((el) => el !== 'hi')
Adding an elmeent to an array: [...state, 'hi']
Replacing an element in an array: state.map((el) => el === 'hi' ? bye : el)

Updating a property in an object: {...state, name: 'Alejandro' }
Adding a property onto an object: {...state, age: 30 }
Removing a property from an object: 

Using Lodash:
const profile = { name: 'Alejandro' }
_.omit(profile, 'name'); // will return {}

DOES NOT MODIFY OUR OBJECT!

### What does the State property in Redux do?
The state property in Redux is a central repository of all the information that has been created by our reducers. All of the information gets consolidated in our react object so that React has access to reach into the Redux part of our applciation and get the appropriate data. 

### How do you modify the state?
The only way to modify the state in your store is to dispatch and action creator to modify it. There is no way to modify it directly. 

### In reducers why do you always want to create a new array rather than modify an old one?
You always want to create a new array rather than modifying the state. This can be done with ...rest operator.

### What is the Store in Redux?
A store in redux is essentially the collection of different reducers and action creators.

### Why use Redux?
As our app becomes bigger, the complexity tends to exponentially rise. With Redux, our app might become more complex from the beginning, but as the application grows, the complexity looks more linear than exponential. 

### What does the react-redux do?
It allows us to combine and use both React and Redux libraries interchangibly. It's the connection to both ui frameworks.

### Named export vs. default export?
A named export allow us to export many different functions from a file. A default export only allows us to export one. export default 'name' doesn't need to be deconstructed when importing. Named exports do need to be deconstructed.

### Whats the purpose of the provider?
The providers single purpose is to "provide" the store inot its child components. The provider esentially wraps the entire applcation giving the accesbility to the store to all the components. 

### Whats the purpose of the Connect Function?
The connect function maps the stores state and dispatches to the props of a component. It passes the JS functions and warps it in anothe function that connects to Redux. Without it, we wouldn't be able to communciate with Redux. 

### Accessing data in Redux?
We can either retrieve data by obtaining its current state, or change its state by dispatching an action.

### What is axios used for?
Axios helps us make network request. 

### What is Redux-thunk?
Redux-thunk is the middleware that helps us make request in a Redux application. It helps us deal with these aynchronous action creators. It helps us solve our async issues. 

Normal rules with React allows action creators to return POJO's, but that's it. 
With Redux-thunk we're action creators are allowed to return POJO's or a function. Redux-thunk automatically calls that function for you (which in most cases is obtaining/fetching data from an API). If you dispatched an action thats a function, it will call the 'dispatch' and 'getState' functions for you as well, eventually passing it down the middleware again.

With Redux thunk we can MANUALLY dispatch an action at some point in time in the future. 

### Redux data fetching (Components and Action Creators)
Components are generally responsible for fetching data they need by calling an action creator. 
Action creators are responsible for making API request (This is where Redux-Thunk comes into play)
We get fetched data into a component by generating new state in our redux store, then getting that data into our components through mapStateToProps.

### If using async/await in your action creator what issues might you encounter?
If no middleware is used, when babel transpiles your code it will return the request from the action creator. When the redux store looks to see what changed, it realizes that it is not a POJO, resulting in errors. What we want to return is the POJO from the fetching of the data. 

### Synchronous Action Creator vs Asynchronous Action Creators
A synchronous action creator returns an action with data ready to go (it will always pass data to reducers).
An asynchronous action takes some amount of time for it to get its data ready to go.

### What is middleware?
A middleware is a plan JS function that is going to be called with every single action that you dispatch. Middleware has the ability to stop or modify an action.

### What is memoization(_lodash) and what does it help with?
Memoization allows us to only make on request to fetch data. Example: If we have to fetch data for users multiple times due to say comments (for each comment), with memoization we would only have to make the request once. Anytime we call it again in the future the function will not run again. This is only based on unique argument that are passed onto the function. 

Helps stop the overfetching issue!!

### lodash methods:
_.map(), _.uniq(), _.memoization(), _.chain() - chain is a special function in lodash that allows us to chain on a bunch of additional functions to manipulate data.

### How does a component get access to data in the Redux store?
The component should be turned into a 'connected component' using a Redux container.

### Which of the following are principles of Redux?
The state of the entire application is stored in an object/ state tree within a single store. State is read-opnly. The only way to change the state is to trigger an action. Changes are made with pure function.

### Debugging with redux dev tools?
You can go to: localhost:3000/?debug_session=logged_in 
This saves all data in your redux store between refreshes on a page.