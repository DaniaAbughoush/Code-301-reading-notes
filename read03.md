# Lifting State Up

* we keep values in  keeps its value in this.state

# Adding a Second Input
* `~const scaleNames = {`
 ` c: 'Celsius',`
 ` f: 'Fahrenheit'`
`};`

`class TemperatureInput extends React.Component {`
  `constructor(props) {`
    `super(props);`
    `this.handleChange = this.handleChange.bind(this);`
    `this.state = {temperature: ''};`
  `}`

  `handleChange(e) {`
   ` this.setState({temperature: e.target.value});`
 ` }`

 ` render() {`
    `const temperature = this.state.temperature;`
    `const scale = this.props.scale;`
    `return (`
     ` <fieldset>`
        `<legend>Enter temperature in {scaleNames[scale]}:</`legend>`
       ` <input value={temperature}`
               `onChange={this.handleChange} />`
     ` </fieldset>`
   ` );`
 ` }`
`}~`

# Writing Conversion Functions:
functions convert numbers. We will write another function that takes a string temperature and a converter function as arguments and returns a string. We will use it to calculate the value of one input based on the other input.

`(function toCelsius(fahrenheit) {`
 ` return (fahrenheit - 32) * 5 / 9;`
`}`
``
`function toFahrenheit(celsius) {`
  ``return (celsius * 9 / 5) + 32;`
`})`

 # Lifting State Up:
 * sharing state is accomplished by moving it up to the closest common ancestor of the components that need it. This is called “lifting state up
 * We know that props are read-only. When the variable was in the local state

 steps:
 * React calls the function specified as onChange on the DOM `<input>.` In our case, this is the handleChange method in the TemperatureInput component.

 * The handleChange method in the TemperatureInput component calls this.props.onTemperatureChange() with the new desired value.
 * When it previously rendered, the Calculator had specified that onTemperatureChange of the Celsius TemperatureInput is the Calculator’s handleCelsiusChange method, 

 * nside these methods, the Calculator component asks React to re-render itself by calling this.setState() with the new input value and the current scale of the input we just edited.
*React calls the Calculator component’s render method to learn what the UI should look like. The values of both inputs are recomputed based on the current temperature and the active scale. The temperature conversion is performed here.
* React calls the render methods of the individual TemperatureInput components with their new props specified by the Calculator. It learns what their UI should look like.
* react calls the render method of the BoilingVerdict component, passing the temperature in Celsius as its props.
* react DOM updates the DOM with the boiling verdict and to match the desired input values. The input we just edited receives its current value, and the other input is updated to the temperature after conversio

**There should be a single “source of truth” for any data that changes in a React application.**

**ifting state involves writing more “boilerplate” code than two-way binding approaches, but as a benefit, it takes less work to find and isolate bugs.**

**When you see something wrong in the UI, you can use React Developer Tools to inspect the props**

# Lists and Keys:
 Rendering Multiple Components:

 can build collections of elements and include them in JSX using curly braces {}

 # Basic List Component:
 * Usually you would render lists inside a component.

* When you run this code, you’ll be given a warning that a key should be provided for list items. A “key” is a special string attribute you need to include when creating lists of elements. We’ll discuss why it’s important in the next section.


Keys help React identify which items have changed, are added, or are removed. Keys should be given to the elements inside the array to give the elements a stable identity:

* The best way to pick a key is to use a string that uniquely identifies a list item among its siblings. Most often you would use IDs from your data as keys:

* When you don’t have stable IDs for rendered items, you may use the item index as a key as a last resor

* on’t recommend using indexes for keys if the order of items may change. This can negatively impact performance and may cause issues with component state

* Keys only make sense in the context of the surrounding array.

# react:
React is a declarative, efficient, and flexible JavaScript library for building user interfaces. It lets you compose complex UIs from small and isolated pieces of code called “components”.

* A component takes in parameters, called props (short for “properties”), and returns a hierarchy of views to display via the render method.
1. Square
1. Board
1. Game
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


  **To collect data from multiple children, or to have two child components communicate with each other, you need to declare the shared state in their parent component instead. The parent component can pass the state back down to the children by using props; this keeps the child components in sync with each other and with the parent component.**

  **use the .slice() method to create a copy of the squares array to copy instead of modifying the existing array.**

  * Data Change without Mutation
  The end result is the same but by not mutating (or changing the underlying data) directly, we gain several benefits described below.


* Complex Features Become Simple:
mmutability makes complex features much easier to implement. 

* Detecting Changes:
Detecting changes in immutable objects is considerably easier. If the immutable object that is being referenced is different than the previous one, then the object has changed.

* Determining When to Re-Render in React:
You can learn more about shouldComponentUpdate() and how you can build pure components by reading Optimizing Performance.
# Function Components:

In React, function components are a simpler way to write components that only contain a render method and don’t have their own state. Instead of defining a class which extends React.

# Taking Turns:
We’ll set the first move to be “X” by default. We can set this default by modifying the initial state in our Board constructor:

# How to Use the Spread Operator (…) in JavaScript:
* The spread operator is a useful and quick syntax for adding items to arrays, combining arrays or objects, and spreading an array out into a function’s arguments.
 * “When ...arr is used in the function call, it ‘expands’ an iterable object arr into the list of arguments.” — JavaScript.info


  What is ... used for?

  *Spread operator to the rescue! It looks similar to rest parameters, also using ..., but does quite the opposite.” — JavaScript.info

  Thespread operator is useful for many different routine tasks in JavaScript, including the following:

 1. Copying an array
1. Concatenating or combining arrays
1. Using Math functions
1. Using an array as arguments
1. Adding an item to a list
1. Adding to state in React
1. Combining objects
1. Converting NodeList to an array



Copying an array:
Using the … spread operator is a convenient way to copy an array or combine arrays,

# Using an array as arguments
* Since the spread operator “spreads” an array into different arguments, any functions that accepts multiple any number of arguments can benefit from use of the spread operator.

# Combining objects
* The spread syntax is useful for combining the properties and methods on objects into a new object:

# A note about copying by reference:
One of the benefits of using the spread operator is that it will create a new reference to its primitive values, copying them.

