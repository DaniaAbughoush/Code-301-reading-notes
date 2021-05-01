# How would you break a mock into a component heirarchy?
The first thing you’ll want to do is to draw boxes around every component, create a new function or object. One such technique is the single responsibility principle, that is, a component should ideally only do one thing. ,Separate your UI into components, where each component matches one piece of your data model.,

# What is the single responsibility principle and how does it apply to components?

ciding if you should create a new function or object. One such technique is the single responsibility principle, that is, a component should ideally only do one thing. If it ends up growing, it should be decomposed into smaller subcomponents.

 displaying a JSON data model to a user, you’ll find that if your model was built correctly, your UI (and therefore your component structure) will map nicely.

 # What does it mean to build a ‘static’ version of your application?
 version requires a lot of typing and no thinking, and adding interactivity requires a lot of thinking and not a lot of typing. We’ll see why.

To build a static version of your app that renders your data model, you’ll want to build components that reuse other components and pass data using props. props are a way of passing data from parent to child. If you’re familiar with the concept of state

# nce you have a static application, what do you need to add?
ou’ll have a library of reusable components that render your data model. The components will only have render() methods since this is a static version of your app. The component at the top of the hierarchy (FilterableProductTable) will take your data model as a prop. If you make a change to your underlying data model and call ReactDOM.render() 

# What are the three questions you can ask to determine if something is state?
Is it passed in from a parent via props? If so, it probably isn’t state.
Does it remain unchanged over time? If so, it probably isn’t state.
Can you compute it based on any other state or props in your component? If so, it isn’t state.

# How can you identify where state needs to live?
ProductTable needs to filter the product list based on state and SearchBar needs to display the search text and checked state.
The common owner component is FilterableProductTable.
It conceptually makes sense for the filter text and checked value to live in FilterableProductTable
Cool, so we’ve decided that our state lives in FilterableProductTable
