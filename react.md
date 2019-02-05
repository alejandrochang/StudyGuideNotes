# React

### What is a presentational component?
A component that does not pass state.

### What are refs in React?
Refs in react are essentially the way we use React to acces Nodes in the DOM, giving access to a single DOM element. 

### Promise versus async await?
They both work using promises, but async await has a few advantages to using it. Async awaits return a promise. 

### Network Request and Fetchning Data, What are the two common ways of doing it?
axios: a third partypackage
fetch: built into modern browsers
promises/async await

### Difference between uncontrolled and controlled component?
Controlled components store their information inside React components such as the state instead of storing it into the DOM. 

### What are the three special event handlers in React and what do they do?
1. onClick = User clicks on something
2. onChange = User changes text in an input tag
3. onSubmit = Users submits a form

### What are Lifecycle methods good for?
constructor: good place to do one-time setup
render: Avoid doing anything nore related to JSX

*Content becomes visible to screen*

componentDidMount: Good place for data-loading

*Sit and wait for updates*

componentDidUpdate: Good place for more data-loading when state/props change
componentWillUnmount: Good place to do cleanup, especially non-React stuff

### What is conditional rendering?
Returning different jsx/content of component based on the state or props changing.

### What is super?
Super is a reference to the parents constructor function. That's why we call super on the constructor because the 'APP' Component or any component for that matter is initially referring to it's parent the React.Component.

### What is state?
State is a JS object that contains data relevant to a component. If we want to get a single component to update itself we're going to update its state. 

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
In React you can have functional components/presentational and class components. Functional components are easier for simple applications, class components are good for just about everything else. 

Functional Components don't have state or lifecycle methods, which is why they're also referred as stateless components.

### Difference between a require statement and an import statement? 
The import statement looks into the node modules and imports it into the file. Import statements come from ES2015 Module System, the require statement comes from CommonJSModules system.  

### What are node modules, package.json, package-lock.json etc?
Node modules include all of our dependencies. Package.json records all of the different dependencies and configures our project. Package-lock.json Records the exact version of the packages we installed. 

### What are typical static files and where are they located?
Static files are typically in a public folder. Static files are never changing so this includes typically index.html, images and audio/mp3 files. 

### What is Babel and why use it?
Babel is a command-line tool that can take any version of JS and spit out a newer version. It allows us to use any JS so it is supported in any browser even if it's not up-to-date. 

### What is JSX and how is it used in React?
JSX is a syntax-extension to JavaScript that has familiar syntax to HTML making it easy-to-use and incorporate both JSX and JS in one file. Java Serialization to XML.

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
- getDerivedStateFromProps
- render
- componentDidMount

Update of the state:
- shouldComponentUpdate
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

### What is state, setState and forceUpdate?

State is the current state of the component. Typically, state can only be used in class-based components, unless you use the hooks system. 

setState() creates changes to the component state and tells React that this component and it's children need to be re-rendered with the updated state. 

setState() does not always immediately update the component. It may defer until later. Thus, use componentDidUpdate() or a setState() callback setState(updater, callback) which guarantees to fire after the update has been applied. 

forceUpdate() : If your component depends on some other data that does not include state/props update or your render() method you can achieve it by calling forceUpdate(). forceUpdate will cause render to be called on the component. 

### CRUD (Create Read Update Destroy)
Talking about different operations to perform on records inside an application. CRUD operations are pretty much in almost every single application.

### React Routers (different dependencty types)
react-router: Core navigation lib - we don't install this manually (typically)
react-router-native: Navigation for react-native apps (native mobile applications)
react-router-redux: Bindings between redux and react-router (not necessary)

* react-router-dom: Navigation for dom-based apps (we will want to use this one almost always)
The react-router-dom allows for navigation.

### How does react-router-dom works ?


### What does the BrowserRouter Component do?
The BrowserRouter internally creates a history object. The history object keeps track of your address bar in your browser. The BrowserRouter listens to the 'history' object for changes to the URL. 

### What is the path property, exact property and component property?
The path property is used by react-router to determine whether or not it will show the component to the screen. The way it extracts information is by using extractedPath.contains(path). If you don't use exact it will show both '/' and '/example' as they're both technically in the path. Using exact will make the path do extractedPath === path which is what we want essentially.

The component property allows you to specifiy which component you will be passing to which specific path.

### Whats are the ways to transition to other pages and what is the best way?
You can transition to other pages using the <a></a> anchor tag, however you don't want to do this as this doesn't work well with react-router-dom. If you user anchor tags the Broswer receives the index.html file and dumps the old HTML file it was showing. This is BAD as it will also dump all the data that you loaded into your react and redux application at the timead. 

You should handle navigation using the Link tag: <Link to="/home">Home Page<Link/> tags as using this way react router prevents the browser from navigating to the new page and fetching the new index.html file. The url still changes -> the 'history' object sees the updated URL, takes URL and sends it to the BrowserRouter which communicates to the URL components. (Technically we are still making use of the <a> element on the screen using the <Link/>)

### What is an SPA(Single Page Applications)?
A single page application is an application that loads a single document. When the user navigates around the page we just demonstrate components based on their interaction with links. 

### What are the three different types of routers that React has available?
- BrowserRouter: React looks for the top level domain (TLD) (.com/.net) or port as the path. ex. localhost:3000/
- HashRouter: Uses everything after the # as the path. ex. localhost:3000/#/page2
- MemoryRouter: Doesn't use the url to track navigation ex. localhost:3000/ With memory router the path doesn't change actively in your browser domain.

A HashRouter is more flexible as it doesn't require special configuriation for your backend server. If you're doing a deployment to Github Pages USE HashRouter to always return the index.html file.

### Connection between Routers and Deployment?
BrowserRouter is one of the most common ways to use to deploy your website. There a lot of websites that make it easy for you to deploy using BrowserROuter. However, if those options aren't accessable, it can be very difficult to deploy. 

### Difference between your development server and a traditional server?
Your development server will serve up your index.html file if there is any errors with fetching a particular path or route, unlike a traditional server which will serve a 404 error of not found if there is no such path defined. 

### What is bundle.js file?
The bundle.js file has all the code for all of our application.

### OAuth 2.0
User idenitification through a 3rd party (Google, Facebook, LinkedIn etc.)
OAuth is not only about user authentication, but it is also about getting all the data that is associated with a particular user such as (gmail, etc.)

What is a list of scopes?
List of 'scopes' is the permission that you're granting a website to work.

### OAuth for Servers vs. OAuth for JS Browser Apps
OAuth for servers is usually used when we have an app that needs to access user data when the user is not logged in
OAuth for JS Browser Apps is usually used when we have an app that needs to access user data only while the user is logged in.

