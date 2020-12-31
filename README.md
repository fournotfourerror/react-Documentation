# react-Documentation

### Prerequisites
* Node (nodejs.org)
* Knowledge on
  * HTML5
  * CSS3
  * JavaScript (ES6)
  
### Babel && WebPack
* All the browsers suppoerts `ES-5`.
* We are using `ES-6` concepts
* Babel is a tranpiler that converts the new JS code to Older ones.


* Minify (CSS, SCSS, SASS, JavaScript)
* WebPack consists of two functionalities
  * Loaders
    * CSS-Loader
    * SASS-Loader
    * Babel-Loader
  * Plugins
  
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

### State in React
_The concept of State provides a way to store the data in a component_

```javascript
  constructor(){
    super();
    this.state={
      "name":"Hanuman",
      "role":"Full stack developer"
    }
  }
```

### Manipulating data from a state
```javascript
 changeStateValues=()=>{
    this.setState({
      "name":"Rajesh",
      "role":"MERN developer"
    })
  }
  render(){
    return(
    <> 
      <Header />
    <h2 onMouseOver={this.changeStateValues}> {this.state.name} working as a {this.state.role} </h2> 
      <App />
    </>
    )
  }
```

#### Using prevState for manipulating the data of a state
```javascript
  incrementCounter=()=>{
    this.setState(prevState=>(
      {counter: prevState.counter+1}
    ))
  }
```

#### Decrementing the value of the state
```javascript
 decrementCounter=()=>{
    if(this.state.counter>0){
    this.setState(prevState=>(
      {counter: prevState.counter-1}
    ))
    }
  }
```

#### Using hooks concept for implementing state functionality in functional component
```javascript
 import React,{useState} from 'react';
// import Header from './Header'



function App(){

  var initialData=()=>{
    setData({
      name:"Hanuman",
      role:"Full stack developer"
    })
  }

  const [data,setData]=useState({"name":"Hanuman","role":"Full stack developer"})
  return(
    <>
      <h2 onMouseOver={()=>{setData({name:"Rajesh",role:"MERN developer"})}} onMouseOut={initialData}> {data.name} is working as a {data.role} </h2>
    </>
  )
}

export default App;
```

#### Applying styles dynamically
```javascript
   import React,{useState} from 'react';
// import Header from './Header'
import './App.css';

function App(){
  var style={
    background:"green"
  }

  var changeBackground=(e)=>{
    e.target.setAttribute('class','changeBackground')
  }

  const [data,setData]=useState({"name":"Hanuman","role":"Full stack developer"})
  return (
    <>
      <h2 onMouseOver={(e)=>{changeBackground(e)}}> {data.name} is working as {data.role}.</h2>
    </>
  )
}

export default App;
```

#### Regular expression in React
```javascript
 import React,{useState} from 'react';

export default function FormInput(){
    function testMobile(e){
        var reg=/^\S+@\S+[.]\S{1,}$/
        if(reg.test(e.target.value)){
            setContent({
                background:"green",
                text:"Valid Email id"
            })
        } else {
            setContent({
                background:"red",
                text:"Invalid Email id"
            })
        }
    }
    var [content, setContent]=useState({background:"#fff",text:"hi"})
    return(
        <div>
            <article style={{background:content.background, textAlign:"center"}}> {content.text} </article> <br />
            <form>
                <input type="text" placeholder="Email id" onKeyUp={(event)=>{testMobile(event)}}/>
            </form>
        </div>
    )
}


```

### Live search from JSON
```javascript
  import React from 'react';
import './App.css'
import {profiles} from './data.json'

export default class Search extends React.Component{
    constructor(){
        super();
        this.state={
            search:""
        }
    }

    searchData=(e)=>{
        this.setState({search: e.target.value})
    }
    render(){
        const {search} =this.state;
        console.log(search)
        const filteredNames=profiles.filter(profileInfo=>{
            return profileInfo.name.toLowerCase().indexOf(search.toLowerCase())!==-1
        })
        return(
            <div className="container">
                <input type="text" placeholder="Search..." onKeyUp={(event)=>{this.searchData(event)}}/>
                <div className="parent">
                    {
                        filteredNames.map((item,index)=>(
                            <div className="child" key={index}>
                                {item.name}    
                             </div>
                        ))
                    }
                </div>
            </div>
        )
    }
}
```

