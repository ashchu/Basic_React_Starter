# Review of React JS
**Using Screen**

/a + /d to leave server running

lsof -wni tcp:3000

kill -9 19587

sudo fuser -k 3000/tcp

### React Tips

If-Statement Rendering:

[https://scotch.io/tutorials/7-ways-to-implement-conditional-rendering-in-react-applications](https://scotch.io/tutorials/7-ways-to-implement-conditional-rendering-in-react-applications)

Quick Overview on React:

[https://www.youtube.com/watch?v=sBws8MSXN7A](https://www.youtube.com/watch?v=sBws8MSXN7A)

Using React Refs:

[https://medium.com/@rossbulat/how-to-use-react-refs-4541a7501663](https://reactjs.org/docs/refs-and-the-dom.html#callback-refs)

Using Props:

[https://itnext.io/what-is-props-and-how-to-use-it-in-react-da307f500da0](https://itnext.io/what-is-props-and-how-to-use-it-in-react-da307f500da0)

State:

[https://reactjs.org/docs/faq-state.html#what-is-the-difference-between-state-and-props](https://reactjs.org/docs/faq-state.html#what-is-the-difference-between-state-and-props)

React Thinking:

[https://reactjs.org/docs/thinking-in-react.html](https://reactjs.org/docs/thinking-in-react.html)

Passing Date in React (Props/State):

[https://medium.com/@ruthmpardee/passing-data-between-react-components-103ad82ebd17](https://medium.com/@ruthmpardee/passing-data-between-react-components-103ad82ebd17)

Binding with CallBack Funcs:

[https://www.andreasreiterer.at/bind-callback-function-react/](https://www.andreasreiterer.at/bind-callback-function-react/)

# React Breakdown

[Overview Reference](https://reactjs.org/docs/react-component.html)

**React Component**

: A component that will be implemented in your React program.<br> Use

```
extends React.Component
```

when defining a class to define a React component class. The only method you must define in a Render.Component subclass is

```
render()
```

. <br>

Don't create your own base class! Code reuse: achieved through composition rather than inheritance.

**Format**

:

```
<ClassName props={} />
```

### When an instance is created

**Constructor():**

Used to initialize local state with

```
this.state
```

and bind even handlers to an instance.

args

: props (any and all args)

- must call `super(props)` before any statement or else `this.props` will be undefined.
- Do not call `this.setstate()` in constructor. You must define this.state in the constructor (`this.state={}`). This is the **only** place you should define `this.state` directly.
- Don't define items directly with values already known (i.e. `color: props.color`) -> redundant

**ComponentDidMount():**

Invoked immediately after component mounted.

What goes here:

- initialization that requires DOM manipulation
- load data from remote endpoint (good plc to initiate network request)
- set up subscriptions
- calling `setState()`

**Render():**

Examines

```
this.props
```

and returns:

- React elements → elements that instruct DOM node render
- Arrays and fragments → Returns multiple elements grouped together (ie elements within `<table>`)
- Portals
- Strings + numbers
- Booleans or null

Advise

- should be pure → doesn't modify the component
- always returns same result
- doesn't directly act with browser

**The only required method. Also does updating.**

**Other APIs**

setState(): enqueues changes to current component state → tells React + children to be re-rendered w/ updates.

Primary way to update state

- Generally called in response to even handlers
- request rather than immediate command for updates
- Potential args: `(state, props)` → state = current component state; props = additional/new properties

**Instance Properties**

- props: `this.props` props defined by caller of component
- state: `this.state` data specific to component (can change over time) → user defined. Never mutate directly.

**Additional Notes**

- [Components + Props](https://reactjs.org/docs/components-and-props.html):
    - components: split UI into isolated pieces; essentially JS functions
        - Accept arbitrary inputs (props)
    - To render component:
        - Use DOM tags
        - Also rep user-defined components
- [State + Lifecycle](https://reactjs.org/docs/state-and-lifecycle.html):

---

**React:**

a JS library used for building UIs from front-end apps

- often called a framework b/c behavior + fairly small
- Why?
    - virtual DOM
    - JSX
    - Interactive UIs
    - self contained, independent components with own state

**TO KNOW Before!**

- JS Fundamentals
- Classes
- Destructuring
- HOF
- Arrow Funcs
- Fetch API/Promises

Everything in UI self-sustained component

- Layered components stacked together

**State**

- Object → determines how component renders + behavrs
- “Application level” state by using a state manager
    - State manager → Redux, context API
- Passed in: **Props**
- Defined within: **State**

CLI Tool “Create-React-App”

- Creates boiler plate app
- Uses Webpack
- bundled with dev server → hot reload
    - auto reloads as you save
- "npm run build“
    - compiles code for browser

**Anatomy of a Component**

- Class-based components
- Can have life cycles
- Returns a .jsx
    - JS Experessions embedded in markup
    - Reference state with diff key-value pairs

**Using arrow functions**

- Why not use standard functions?
    - reads  as undefined thus can’t use.

        props

**Bind**

- Allows you to reference a specific structure

**IMPORTANT**

- **NEVER EVER EVER call setState in componentWillUnmount**
- Utilize
