# react-Documentation

### Prerequisites
* Node (nodejs.org)
* Knowledge on
  * HTML5
  * CSS3
  * JavaScript (ES6)
  
### Installation
`node -v`

`npm -v`

`npm install create-react-app -g`

`create-react-app <project_name>`

`npx create-react-app <project_name>`

### Components in React
* Class components
 * For representing a class component we have to use `class` keyword
 * `render()` for returning a statement
 * We have to aquire the properties from base class for implementing.
 
* Functional components
 * We have to use `function` | `()=>` for implementing a functional component
 * Can return a statement directly
 * High performance than class Component

### Styling components
```javascript
  // Inline styles
  <h2 style={{backgroundColor:"green"}}> Sample content </h2>`
  
  // Stying component using JavaScript object
  var style={
     backgroundColor: "reg",
     color: "#000"
   }
```

### Composition
_The process of combining multiple components together_

### React fragment
_We have to use react fragments for avoiding number of divisions._
```javascript
   <React.Fragment>
    <Header />
    <h2> Sample heading </h2>
   </React.Fragment>
   
   or
   
   <> 
      <Header />
      <h2> Hellow world </h2> <h2> Hi everyone</h2> 
      <App />
    </>
```
