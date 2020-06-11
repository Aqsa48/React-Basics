## Type checking a Component's Props with  `PropTypes`

As we implement additional features into our app, we may soon find ourselves debugging our components more frequently. For example, what if the  `props`  that we pass to our components end up being an unintended data type (e.g. an object instead of an array)? PropTypes is a package that lets us define the data type we want to see right from the get-go and warn us during development if the prop that's passed to the component doesn't match what is expected.

Install By 
```
npm install --save prop-types```
yarn add prop-types

// This is file which will show you on echo whatever you type  

functional Controll compoennets
import React, { Component } from 'react';
import PropTypes from 'prop-types';
import logo from './logo.svg';
import './App.css';

class App extends Component {
   static propTypes = {
  *** //for function contacts= PropTypes.func.isRequired,
      //for Array contacts=PropTypes.array,isRequired***
    }
 
    state = {
    query: ''
}

 updateQuery = (query) => {
    this.setState(() => ({
      query: query.trim()
    }))
  }
  render() { 
    return (
      <div className="App">
        <header className="App-header">
          <img src={logo} className="App-logo" alt="logo" />
          <h1 className="App-title">ReactND - Coding Practice</h1>
        </header>
        <div className="container">
    
         <input
            className='search-contacts'
            type='text'
            placeholder='Search Contacts'
            value={this.state.query}
            onChange={(event) => this.updateQuery(event.target.value)}
          />
          <p className="echo">Echo:</p>
          <p>This should mirror the text you typed into the input field. {this.state.query}</p>
        </div>
      </div>
    );
  }
}
export default App;

