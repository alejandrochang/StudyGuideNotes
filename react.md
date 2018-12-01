# React

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

###