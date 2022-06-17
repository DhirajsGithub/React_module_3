# Diving Deeper : Working with Fragments, Portals and Refs

# Fragments : 
* Jsx limitations --> You can't return more than one root jsx element you also can't store more than one root jsx element in a variable
* The solution --> always wrap adjacent element with div or any element 
returning an array of elements will also do the trick, but need to add a specific key to each returning element
* A new problem --> div soup --> by wrapping means we some time end with unnecessary wrapping div's which will make our programming slower to render such unnecessary element and sometimes can affect our wrappig style
* We can make a Helper directory and can make a wrapper.js file while only return props.children, then the fileName can be used as wrapper instead of div
* But <React.Fragment>what you return<React.Fragment> is used oftenly

# Refs (react hook) : 
* refs in react --> another react hooks, react hooks only work inside the component function
Refs are a function provided by React to access the DOM element and the React element that you might have created on your own. They are used in cases where we want to change the value of a child component, without making use of props and all.
* when you only want to read value and you don't need to change the value then use useRef();
Avoid using refs for anything that can be done declaratively.

# Portals : 
* understaning react portals -->
Portals provide a first-class way to render children into a DOM node that exists outside the DOM hierarchy of the parent component.
any nested component if we want it next to any other component to render we use react portals
to create a port we use <br>
`<div id="backdrop-root"></div> ` <br>
`<div id="overlay-root"></div>`<br>
in index.html next to the body tag <br>
then wrap your component like this : 
<code> {ReactDOM.createPortal(
      <Backdrop onConfirm={props.onConfirm} />,
      document.getElementById('backdrop-root'))}
      
 </code>


# Why React and ReactDom
The reason React and ReactDOM were split into two libraries was due to the arrival of React Native. React contains functionality utilised in web and mobile apps. ReactDOM functionality is utilised only in web apps.
