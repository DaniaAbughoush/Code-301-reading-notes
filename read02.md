# Converting a Function to a Class:
1. import React from 'react'
1. class App extends React.Component
1. render()
1. return
1. contain element in div
1. this.props for passing values

* rendered component to the DOM for the firs time . called “mounting” in React.

* the DOM produced by the component is removed. This is called “unmounting” in React.

  # “lifecycle methods”.:
   when a component mounts and unmounts.

   * Neither parent nor child components can know if a certain component is stateful or stateless, and they shouldn’t care whether it is defined as a function or a class.
   * This is why state is often called local or encapsulated. It is not accessible to any component other than the one that owns and sets it.
   

   # Handling Events:
   1. React events are named using camelCase, rather than lowercase.
   2. With JSX you pass a function as the event handler, rather than a string.
   3. cannot return false to prevent default behavior in React. You must call preventDefault explicitly
   4. don’t need to call addEventListener to add listeners to a DOM element after it is created.

   to avoid  different callback from creating each time the component renders and extra re-rendering. **use constructor or using the class fields syntax**


   # Passing Arguments to Event Handlers:
   use arrow functions and Function.prototype.bind

   # Conditional Rendering:
   **Conditional rendering in React works the same way conditions work in JavaScript.**

   ` function Greeting(props) {
  const isLoggedIn = props.isLoggedIn;
  if (isLoggedIn) {
    return <UserGreeting />;
  }
  return <GuestGreeting />;
}

ReactDOM.render(
  // Try changing to isLoggedIn={true}:
  <Greeting isLoggedIn={false} />,
  document.getElementById('root')
);`


# Element Variables:
* ou can use variables to store elements.

* Inline If with Logical && Operator
wrapping them in curly braces. This includes the JavaScript logical && operator. 
` function Mailbox(props) {
 ` const unreadMessages = props.unreadMessages;`
  `return (`
    `<div>`
      `<h1>Hello!</h1>`
      `{unreadMessages.length > 0 &&`
       ` <h2>`
         ` You have {unreadMessages.length} unread messages.`
        `</h2>`
    `  }`
    `</div>`
  `);`
`}`

`const messages = ['React', 'Re: React', 'Re:Re: React'];`
`ReactDOM.render(`
  `<Mailbox unreadMessages={messages} />,`
  `document.getElementById('root')`
`);`

* Inline If-Else with Conditional Operator:
`condition ? true : false.`
`render() {`
 ` const isLoggedIn = this.state.isLoggedIn;`
`  return (`
    `<div>`
     ` The user is <b>{isLoggedIn ? 'currently' : 'not'}</b> logged in.`
    `</div>`
 ` );`
`}`

- Preventing Component from Rendering:
to do this return null instead of its render output.

# Intro to React

* React is a declarative, efficient, and flexible JavaScript library for building user interfaces. It lets you compose complex UIs from small and isolated pieces of code called “components”.

* A component takes in parameters, called props (short for “properties”), and returns a hierarchy of views to display via the render method.
1. Square
1. Board
1. Game



* 
* build tiktok:
1. starter code:
`class Square extends React.Component {`
 ` render() {`
   ` return (`
      `<button className="square">`
        `{/* TODO */}`
      `</button>`
    `);`
  `}`
`}`

`class Board extends React.Component {`
  `renderSquare(i) {`
    `return <Square />;`
  `}`
2. Making an Interactive Component

Why Immutability Is Important?
There are generally two approaches to changing data. The first approach is to mutate the data by directly changing the data’s values. The second approach is to replace the data with a new copy which has the desired changes.

1. Immutability makes complex features much easier to implement
 * Detecting Changes
 * Detecting changes in mutable objects is difficult because they are modified directly.

 # Rebuilt with React:
 As one of the oldest React libraries, React-Bootstrap has evolved and grown alongside React, making it an excellent choice as your UI foundation.

 # Bootstrap at its core:
 By relying entirely on the Bootstrap stylesheet, React-Bootstrap just works with the thousands of Bootstrap themes you already love.

 # Accessible by default:
 The React component model gives us more control over form and function of each component.

 * Netlify makes CI/CD, deployment and scaled hosting a commodity and helps enterprises focus on creating great dynamic consumer experiences in a Jamstack world.


