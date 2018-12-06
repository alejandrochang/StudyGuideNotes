# React

### What are props?
Props is a system for passing data from a parent component to a child component. The ultimate goal is customize or configure a child component. Either customize how the component looks or how the user interacts with it. 

### What is component hierachy?
Component hierachy is a diagram that tells the different components that are being diplayed in our application and the relationship for those different components.

### How to create a reusable configurable component?
1. Identify the repettitive JSX
2. Descriptive name for what it does (What is it's purpose)
3. New file for component
6. Make it configurable by using React's props system

### Difference between component Nesting, Reusability and Configuration?
Component nesting refers to when a component can be shown inside another component. 
Component reusability is when we make a component that can easily be reused in our application.
Component Configuration refers to the ability for a component to be configured once its created. 

### Difference between class and className?
Instead of using class use className for jsx. You want to avoid using class so you dont collide with class components. 

### What are the two different types of components in React?
In React you can have functional components and class components. Functional components are easier for simple applications, class components are good for just about everything else. 

### Difference between a require statement and an import statement? 
The import statement looks into the node modules and imports it into the file. Import statements come from ES2015 Module System, the require statement comes from CommonJSModules system.  

### What are node modules, package.json, package-lock.json etc?
Node modules include all of our dependencies. Package.json records all of the different dependencies and configures our project. Package-lock.json Records the exact version of the packages we installed. 

### What are typical static files and where are they located?
Static files are typically in a public folder. Static files are never changing so this includes typically index.html, images and audio/mp3 files. 

### What is Babel and why use it?
Babel is a command-line tool that can take any version of JS and spit out a newer version. It allows us to use any JS so it is supported in any browser even if it's not up-to-date. 

### What is JSX and how is it used in React?
JSX is a syntax-extension to JavaScript that has familiar syntax to HTML making it easy-to-use and incorporate both JSX and JS in one file. 

### Difference between React and ReacDOM libraries?
React knows what a component is and how to make components work together. 
ReactDOM knows how to take a component and make it show up in the DOM. 

### Which React Life Cycle Methods can call this.setState()?
The react life cycle methods that can call this.setState() include componentDidUpdate(), componentDidMount(), componentWillReceiveProps() - deprecated and componentWillMount(). 

If using componentWillMount() it is recommended to use the constructor instead to set your state. 

### What is the React life cycle and it's methods?
A react components lifecycle begins with mounting, updating and unmounting. The mounting provides the initial rendering. The updating is the phase where the state and the props can get updated and the unmounting is when that component is essentially discarded. 

Initial Rendering - Mounting:
- constructor
- componentWillMount
- render
- componentDidMount

Update of the state:
- shouldComponentUpdate
- componentWillUpdate
- render
- componentDidUpdate

Update of the props:
- componentWIllReceiveProps
- shouldComponentUpdate
- componentWillUpdate
- render
- componentDidUpdate

Unmounting:
- componentWillUnmount

Error Handling:
-componentDidCatch

### Why is super called in the constructor?
Super is called in the constructor so our class extends to any other class that also has a defined constructor. This special function calls the constructor of our parent class and allows it to initialize itself. 
* This is why we have accewess to this.props only after we've initially called super.

### What is setState and forceUpdate?

setState() creates changes to the component state and tells React that this component and it's children need to be re-rendered with the updated state. 

setState() does not always immediately update the component. It may defer until later. Thus, use componentDidUpdate() or a setState() callback setState(updater, callback) which guarantees to fire after the update has been applied. 

forceUpdate() : If your component depends on some other data that does not include state/props update or your render() method you can achieve it by calling forceUpdate(). forceUpdate will cause render to be called on the component. 

# Redux

### How does a component get access to data in the Redux store?
The component should be turned into a 'connected component' using a Redux container.

### Which of the following are principles of Redux?
The state of the entire application is stored in an object/ state tree within a single store. State is read-opnly. The only way to change the state is to trigger an action. Changes are made with pure function.
