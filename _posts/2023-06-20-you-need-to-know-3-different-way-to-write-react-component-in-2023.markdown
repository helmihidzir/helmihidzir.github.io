---
layout: post
title:  "You need to know 3 different way to write React component in 2023"
date:   2023-06-20 22:00:00 +0800
categories: React
---

##### **Functional component**

```react
import React from "react"

export default function App() {
    const [goOut, setGoOut] = React.useState("Yes")
    
    function toggleGoOut() {
        setGoOut(prevState => {
            return prevState === "Yes" ? "No" : "Yes"
        })
    }
    
    return (
        <div className="state">
            <h1 className="state--title">Should I go out tonight?</h1>
            <div className="state--value" onClick={toggleGoOut}>
                <h1>{goOut}</h1>
            </div>
        </div>
    )
}
```

##### **Class component with [class fields](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/Public_class_fields){:target="_blank"}**

```react
import React from "react"

export default class App extends React.Component {
    // class field
    state = {
        goOut: "Yes"
    }
    
    // need to use arrow function because of Uncaught TypeError: 
    // Cannot read properties of undefined (reading 'setState')
    toggleGoOut = () => {
        this.setState(prevState => {
            return {
                goOut: prevState.goOut === "Yes" ? "No" : "Yes"
            }
        })
    }
    
    render() {
        return (
            <div className="state">
                <h1 className="state--title">Should I go out tonight?</h1>
                <div className="state--value" onClick={this.toggleGoOut}>
                    <h1>{this.state.goOut}</h1>
                </div>
            </div>
        )
    }
}
```

##### **Class component with constructor method**

```react
import React from "react"

export default class App extends React.Component {
    // constructor
    constructor() {
        super() 
        this.state = {
            goOut: "Yes"
        }
    }
    
    toggleGoOut = () => {
        this.setState(prevState => {
            return {
                goOut: prevState.goOut === "Yes" ? "No" : "Yes"
            }
        })
    }
    
    render() {
        return (
            <div className="state">
                <h1 className="state--title">Should I go out tonight?</h1>
                <div className="state--value" onClick={this.toggleGoOut}>
                    <h1>{this.state.goOut}</h1>
                </div>
            </div>
        )
    }
}
```
