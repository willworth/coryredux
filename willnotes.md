## eslint
0 off 1 warning 2 error

doesn't currently watch files needs a separate cmd
"lint:watch": "npm run lint -- --watch"
## npm run all
for parallel scripting!

will run all that follow parallel
`"start": "npm-run-all --parallel test:watch open:src lint:watch",`


# react component approaches


### es5 class component

var HelloWorld = React.createClass({
  render: funtion(){
    return (
      <h1>Hello World</h1>
    );
  }
});

still works, but better to use

###  es6

no autobind
context of this varies depending on the caller
recommend binding to constructor

default props declared separately

set init state in contructors

### es6 stateless functional components

const HelloWorld = (props) => {
  return (
      <h1>Hello World</h1>
    );
};

### benefits of stateless functional components
no class needed
allows you to avoid "this"
enforced best practices
easy to test



### class versus stateless
when use class:
when you need state!
if you need refs
if you need lifecycle methods
child functions (for performance)


stateless:
everywhere else!



==========================

## container and presentation components

### container
little to no markup
concerned with behaviour marshalling data and actions
"the backend of the front end"
pass data and actions down
know about redux
often stateful

### presentation  // most should be this category
dumb
ie nearly all markup
no logic!
receive data and actions via props
don't know about redux (normally)
typically stateless functional components


container       | presentational
smart           | dumb
Stateful        | stateless
controller view | view



App.js is main entry point.
it passes down the children it receives as props
children will be passed in from react router
