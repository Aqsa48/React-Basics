## Class Components vs. Stateless Functional Components


#### #1 Stateless Components

```javascript
const Repos = React.createClass({
  render(){
    return (
      <div>
        <h3> User Repos </h3>
        <ul className="list-group">
          {this.props.repos.map((repo, index) => {
            return (
              <li className="list-group-item" key={repo.name}>
                <h4><a href={repo.html_url}>{repo.name}</a></h4>
                <p>{repo.description}</p>
              </li>
            )
          })}
        </ul>
      </div>
    )
  }
})

class Repos extends React.Component {
  render(){
    return (
      <div>
        <h3> User Repos </h3>
        <ul className="list-group">
          {this.props.repos.map((repo, index) => {
            return (
              <li className="list-group-item" key={repo.name}>
                <h4><a href={repo.html_url}>{repo.name}</a></h4>
                <p>{repo.description}</p>
              </li>
            )
          })}
        </ul>
      </div>
    )
  }
}
```

All the code above does is it receives an array of repositories of a specific user, maps over those repositories, and displays them to the view.

You should feel pretty at home with the code above.  _createClass_  has been around since the heavens opened and bestowed React upon us and  _React.Component_  has been around since React 0.13.0 Beta 1 (January 2015). Neither component is using getInitialState or a constructor to initialize a state property. Each component is receiving its data as props then simply presenting that data.

#### #2 Stateless Functional Components

```javascript
const Repos = ({repos}) => {
  return (
    <div>
      <h3> User Repos </h3>
      <ul className="list-group">
        {repos.map((repo, index) => {
          return (
            <li className="list-group-item" key={repo.name}>
              <h4><a href={repo.html_url}>{repo.name}</a></h4>
              <p>{repo.description}</p>
            </li>
          )
        })}
      </ul>
    </div>
  )
}
```

Notice the code above is just a function (granted a fancy ES6 function but that’s besides the point). If your component has just a  _render_  method (and no state), you can simply create your component as a  _Stateless Functional Component_  and your function will be passed  _props_  as its first argument. Also notice that we’re NOT calling this a* Stateless Component* or a  _Functional Component_. The reason for that brings us to number 3.







#3 Functional Components


