# protJS
Opt-In prototype helper functions

This toolset was designed to provide the ease-of-use and legibility of prototypal methods, without actually modifying the core objects, or bloating all variables of that constructor type. It does this by providing short-hand 'wrappers' for different data types which extend JavaScript's native functionality during those chained calls.

The wrappers currently available:
  - Array: `A(myArray)` or `A([1,2,3])`
  - Object: `O(myObj)` or `O({a:1, b:2})`
  - String: `S(myStr)` or `S("some string")`
  - Node: `N(myNode)` or `N("node selector")`
  - Event: `E(event)`
  - Number/Digits: `D(myNum)` or `D(3.5)`
  
It also includes some standard functions used internally, but also useful outside of the wrappers:
  - `df(variable)` - returns whether or not `variable` is defined.
    - `df(variable,"boolean")` - returns whether or not `variable` is of type "boolean"
    - `df(variable,"boolean",true)` - returns `variable` if it is boolean, otherwise returns `true`
  - `addEvent(element,'click',callback)` - attaches the `callback` to a `click` event on the `element`, selecting `addEventListener` or `attachEvent` as appropriate
  - `getEvent(event)` - returns the same event object (or window.event if invalid), but ensures that `event.target` is set (basically just a safe event referencer in an event handler when supporting older browsers)
