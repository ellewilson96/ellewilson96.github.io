---
layout: post
title:      "React Data Flow with Redux"
date:       2019-01-02 14:36:39 +0000
permalink:  react_data_flow_with_redux
---


As I am researching more and more about React and Redux, I wanted to share my thoughts and try to explain the data flow within React/Redux applications. This was the topic that caused the most frustration for me, so now that I understand it better, I will try to outline my thoughts in the way that makes the most sense for me.

# Connect the Dots

As you initially connect your application to Redux, you must create a store which will be responsible for storing all state objects from each Component. 

The store is passed a reducer as an argument, which is often many reducers combined into a single reducer - often called rootReducer. The store may also take in Redux middleware - an example would be Thunk - and is then instantiated within a Provider. 

The Provider wraps the rendered App component, making all of the application state objects in the store visible to all of the application's container Components.

The container Components are now able to access data from the store, by importing the part of state needed and setting it as props in mapStateToProps().

Right now, there is no data as we have not defined our reducers or actions...

# Retrieving Data from Your API

The action is responsible for actually making the request to the API server. After a successful response, the dispatch will have two objects - the action's type and the retrieved data in a return statement. The action response must then be connected to props, in mapDispatchToProps(), in order to separate concerns so that the component does not have knowledge of the store. 

I was able to omit mapDispatchToProps() from my container Component by simply importing the action object, and then passing it in as a second argument to connect. 

The reducers are responsible for indicating which action needs to occur, based on the action type. Each reducer has an argument of state, set to an empty array, so that state can be set to the action's data response to be passed to the container Component. Reducers are therefore also responsible for updating state.

# Helpful Links
[Getting Started with Redux](https://redux.js.org/introduction/getting-started)

[Getting Started - React](https://reactjs.org/docs/getting-started.html)

[Learn - When To Connect React and Redux](https://learn.co/tracks/full-stack-web-development-v6/redux/react-redux-continued/when-to-connect-react-and-redux)

[Learn - Map Dispatch To Props](https://learn.co/tracks/full-stack-web-development-v6/redux/redux-library/map-dispatch-to-props)

[React Application Data Flow with Redux](https://medium.com/@ajaykarwal/react-application-data-flow-with-redux-1ad51aa4ac45)




