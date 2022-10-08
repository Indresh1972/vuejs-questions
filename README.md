# vuejs-questions

### What is VueJS?
Vue.js is an open-source, progressive Javascript framework for building user interfaces that aim to be incrementally adoptable. The core library of VueJS is focused on the view layer only, and is easy to pick up and integrate with other libraries or existing projects. The most recent version of Vue.js as of November 2018 is version 2.
### What are the major features of VueJS?
Below are the some of major features available with VueJS
 1. **Virtual DOM:** It uses virtual DOM similar to other existing frameworks such as ReactJS, Ember etc. Virtual DOM is a light-weight in-memory tree representation of the original HTML DOM and updated without affecting the original DOM.
 2. **Components:** Used to create reusable custom elements in VueJS applications.
 3. **Templates:** VueJS provides HTML based templates that bind the DOM with the Vue instance data
 4. **Routing:** Navigation between pages is achieved through vue-router
 5. **Light weight:** Vue is a light-weight library compared to other frameworks
 6. **Transitions:**
 7. **Reactivity:**
### What are the lifecycle hooks or methods in VueJS?
 1. **beforeCreate:** This is called synchronously after the Vue instance has been initialized. The beforeCreate hook runs at the very initialization of your component. data has not been made reactive, and events have not been set up yet.
 2. **created:** This is called synchronosly after the Vue instance is created. In the created hook, you will be able to access reactive data and events are active. Templates and Virtual DOM have not yet been mounted or rendered.
 3. **beforeMount:** This is called right before the component is mounted. This hook runs right before the initial render happens and after the template or render functions have been compiled. Most likely you'll never need to use this hook. This doesn't get called when doing server-side rendering.
 4. **mounted:** This is called after the component has just been mounted. You will have full access to the reactive component, templates, and rendered DOM (via this.$el). Mounted is the most-often used lifecycle hook. The most frequentl used patterns are fetching data for your componen (use created for this instead) and modifying the DOM, ofter to integrate non-Vue libraries.
 5. **beforeUpdated:** This is called when the data changes, before the virtual DOM is re-rendered. This hook runs after data changes on your component and the update cycle begins, right before the DOM is patched and re-rendered. It allows you to get the new state of any reactive data on your component before it actually get rendered.
 6. **updated:** This is called after data changes on your component and the DOM re-renders. If you need to access the DOM after a property change, here is probably the safest place to do it.
 7. **activated:** This is called when a keep/kept alive component is activated.
 8. **deactivated:** This is called when a keep/kept alive component is deactivated.
 9. **beforeDestroy:** This is called right before a Vue instance is torn down. Your component will still be fully present and functional. If you need to cleanup events or reactive subscriptions, beforeDestroy would probably be the time to do it.
 10. **destroyed:** This is called after a Vue instance has been destroyed and there's pretty much nothing left on your component. Everything that was attached to it has been destroyed. You might use the destroyed hook to do any last-minute cleanup or to inform a remote server that the component was destroyed. 

### What are the conditional directives?
VueJS provides set of directives to show or hide elements based on conditions. The available directives are: ** v-if, v-else, v-else-if and v-show**
**1. v-if:**  The v-if directive adds or removes DOM elements based on the given expression. For example, the below button will not show if isLoggedIn is set to false.
```javascript
<button v-if="isLoggedIn">Logout</button>
```
You can also control multiple elements with a single v-if statement by wrapping all the elements in a <template> element with the condition. For example, you can have both label and button together conditionally applied,
```javascript
<template v-if="isLoggedIn">
  <label> Logout </button>
  <button> Logout </button>
</template>
```
**2. v-else:**  This directive is used to display content only when the expression adjacent v-if resolves to false. This is similar to else block in any programming language to display alternative content and it is preceded by v-if or v-else-if block. You don't need to pass any value to this.
For example, v-else is used to display LogIn button if isLoggedIn(not logged in) is set to false.
```javascript
<button v-if="isLoggedIn"> Logout </button>
<button v-else> Log In </button>
```
**3. v-else-f:** This directive is used when we need more than two options to be checked.
For example, ifLoginDisabled property is disabled then we need to prevent user to login instead just display the label. This can be achieved through v-else statement.
```javascript
<button v-if="isLoggedIn"> Logout </button>
<label v-else-if="isLoginDisabled"> User login disabled </label>
<button v-else> Log In </button>
```

**4. v-show:** This directive is similar to v-if but it renders all elements to the DOM and then uses the CSS display property to show/hide elements. This directive is recommended if the elements are switched on and off frequently.
```javascript
<span if-show="user.name">Welcome user,{{user.name}}</span>
```
### What is the difference between v-show and v-if directives?
Below are some of the main differences between between **v-show** and **v-if** directives,
1. v-if only renders the element to the DOM if the expression passes whereas v-show renders all elements to the DOM and then uses the CSS display property to show/hide elements based on expression.
2. v-if supports v-else and v-else-if directives whereas v-show doesn't support else directives.
3. v-if has higher toggle costs while v-show has higher initial render costs. i.e, v-show has a performance advantage if the elements are switched on and off frequently, while the v-if has the advantage when it comes to initial render time.

### What are some advantages and disadvantages of Vue?
Advantages
1. Easy for applications and interface development
2. Support for two-way data binding similar to Angular
3. Ability to controls states
4. Natural thought process
5. The framework is light
6. Minimal documentation
7. Easy to understand
Disadvantages
1. Limited scope
2. Single creator
3. Small developer community

### Ref Link:
[http://stackoverflow.com/questions/20822022/javascript-variable-definition-declaration](http://stackoverflow.com/questions/20822022/javascript-variable-definition-declaration)
### How do you empty an array in JavaScript?
For instance, say we have:

```javascript
var arrayList =  ['a', 'b', 'c', 'd', 'e', 'f'];
```

How can we empty the array above?

There are a couple of ways by which we can empty an array, So let's discuss all the possible way by which we can empty an array.

#### Method 1

```javascript
arrayList = [];
```

The code above will set the variable `arrayList` to a new empty array. This is recommended if you don't have **references to the original array** `arrayList` anywhere else because It will actually create a new empty array. You should be careful with this way of empty the array, because if you have referenced this array from another variable, then the original reference array will remain unchanged, Only use this way if you have only referenced the array by its original variable `arrayList`.

For instance:

```javascript
var arrayList = ['a', 'b', 'c', 'd', 'e', 'f']; // Created array
var anotherArrayList = arrayList;  // Referenced arrayList by another variable
arrayList = []; // Empty the array
console.log(anotherArrayList); // Output ['a', 'b', 'c', 'd', 'e', 'f']
```

#### Method 2

```javascript
arrayList.length = 0;
```

The code above will clear the existing array by setting its length to 0. This way of emptying an array will also update all the reference variables that point to the original array. 

For instance:

```javascript
var arrayList = ['a', 'b', 'c', 'd', 'e', 'f']; // Created array
var anotherArrayList = arrayList;  // Referenced arrayList by another variable
arrayList.length = 0; // Empty the array by setting length to 0
console.log(anotherArrayList); // Output []
```

#### Method 3

```javascript
arrayList.splice(0, arrayList.length);
```

Above implementation will also work perfectly. This way of empty the array will also update all the references of the original array.

```javascript
var arrayList = ['a', 'b', 'c', 'd', 'e', 'f']; // Created array
var anotherArrayList = arrayList;  // Referenced arrayList by another variable
arrayList.splice(0, arrayList.length); // Empty the array by setting length to 0
console.log(anotherArrayList); // Output []
```

#### Method 4

```javascript
while(arrayList.length) {
  arrayList.pop();
}
```

Above implementation can also empty the array. But not recommended to use often.
### What is the difference between declaring a function in the formats listed?
```javascript
var foo = function() {
  // Some code
}
```

```javascript
function bar () {
  // Some code
}
```

The main difference is function `foo` is defined at `run-time` and is called function expression, whereas function `bar` is defined at parse time and is called function statement. To understand in better, let's see below code :

```javascript
// Run-Time function declaration
  foo(); // Call foo function here, It will give an error
  var foo = function() {
    console.log("Hi I am inside Foo");
  };
```

```javascript
// Parse-Time function declaration
bar(); // Call bar function here, It will not give an Error
function bar() {
  console.log("Hi I am inside Foo");
}
```

### What are Service Workers and when can you use them?
It’s a technology that allows your web application to use cached resources first, and provide default experience offline, before getting more data from the network later. This principle is commonly known as Offline First.

Service Workers actively use promises. A Service Worker has to be installed,activated and then it can react on fetch, push and sync events.

As of 2017, Service Workers are not supported in IE and Safari.

### What is the difference between a method and a function in javascript?
In JS, that difference is quite subtle. A function is a piece of code that is called by name and function itself not associated with any object and not defined inside any object. It can be passed data to operate on (i.e. parameter) and can optionally return data (the return value).

```javascript
// Function statement
function myFunc() {
  // Do some stuff;
}

// Calling the function
myFunc();
```

Here myFunc() function call is not associated with object hence not invoked through any object.

A function can take a form of immediately invoked function expression (IIFE):

```javascript

// Anonymous Self-invoking Function
(function() {
  // Do some stuff;
})();
```

Finally there are also arrow functions: 

```javascript
const myFunc = arg => {
    console.log("hello", arg)
} 
```

A method is a piece of code that is called by its name and that is associated with the object. Methods are functions. When you call a method like this `obj1.myMethod()`, the reference to `obj1` gets assigned (bound) to `this` variable. In other words, the value of `this` will be `obj1` inside `myMethod`. 

Here are some examples of methods: 

##### Example 1
```javascript
var obj1 = {
  attribute: "xyz",
  myMethod: function () {  // Method
    console.log(this.attribute);
  }
};

// Call the method
obj1.myMethod();
```

Here `obj1` is an object and `myMethod` is a method which is associated with `obj1`.

##### Example 2
In ES6 we have classes. There the methods will look like this:

```javascript
class MyAwesomeClass {
  myMethod() {
    console.log("hi there");
  }
}

const obj1 = new MyAwesomeClass();
obj1.myMethod();
```

Understand: the method is not some kind of special type of a function, and it's not about how you declare a function. It's the way we **call** a function. Look at that: 

```javascript
var obj1 = {
  prop1: "buddy"
}; 
var myFunc = function () {
  console.log("Hi there", this);
};
// let's call myFunc as a function: 
myFunc(); // will output "Hi there undefined" or "Hi there Window"
 
obj1.myMethod = myFunc;
//now we're calling myFunc as a method of obj1, so this will point to obj1
obj1.myMethod(); // will print "Hi there" following with obj1. 

```
### What is IIFE (Immediately Invoked Function Expression) and how it can be useful?
#### Definition
IIFE a function that runs as soon as it's defined. Usually it's anonymous (doesn't have a function name), but it also can be named. Here's an example of IIFE:

```javascript
(function() {
  console.log("Hi, I'm IIFE!");
})();
// outputs "Hi, I'm IIFE!"
```
#### Explanation

So, here's how it works. Remember the difference between function statements (`function a () {}`) and function expressions (`var a = function() {}`)? So, IIFE is a function expression. To make it an expression we surround our function declaration into the parens. We do it to explicitly tell the parser that it's an expression, not a statement (JS doesn't allow statements in parens).

After the function you can see the two `()` braces, this is how we run the function we just declared. 

That's it. The rest is details.  
- The function inside IIFE doesn't have to be anonymous. This one will work perfectly fine and will help to detect your function in a stacktrace during debugging: 
  ```javascript
  (function myIIFEFunc() {
    console.log("Hi, I'm IIFE!");
  })();
  // outputs "Hi, I'm IIFE!"
  ```
- It can take some parameters:
  ```javascript
  (function myIIFEFunc(param1) {
    console.log("Hi, I'm IIFE, " + param1);
  })("Yuri");
  // outputs "Hi, I'm IIFE, Yuri!"
  ```
  Here there value `"Yuri"` is passed to the `param1` of the function.
- It can return a value: 
  ```javascript
  var result = (function myIIFEFunc(param1) {
    console.log("Hi, I'm IIFE, " + param1);
    return 1;
  })("Yuri");
  // outputs "Hi, I'm IIFE, Yuri!"
  // result variable will contain 1
  ```
- You don't have to surround the function declaration into parens, although it's the most common way to define IIFE. Instead you can use any of the following forms: 
  - `~function(){console.log("hi I'm IIFE")}()`
  - `!function(){console.log("hi I'm IIFE")}()`
  - `+function(){console.log("hi I'm IIFE")}()`
  - `-function(){console.log("hi I'm IIFE")}()`
  - `(function(){console.log("hi I'm IIFE")}());`
  - `var i = function(){console.log("hi I'm IIFE")}();`
  - `true && function(){ console.log("hi I'm IIFE") }();`
  - `0, function(){ console.log("hi I'm IIFE") }();`
  - `new function(){ console.log("hi I'm IIFE") }`
  - `new function(){ console.log("hi I'm IIFE") }()`
  
  Please don't use all these forms to impress colleagues, but be prepared that you can encounter them in someone's code. 

### How do you use v-for directive with a range?
     You can also use integer type(say 'n') for `v-for` directive which repeats the element many times.
     ```javascript
     <div>
       <span v-for="n in 20">{{ n }} </span>
     </div>
     ```
     It displays the number 1 to 20.
     
### How do you use v-for directive on template?

Just similar to v-if directive on template, you can also use a `<template>` tag with v-for directive to render a block of multiple elements.

     Let's take a todo example,
     ```javascript
     <ul>
       <template v-for="todo in todos">
         <li>{{ todo.title }}</li>
         <li class="divider"></li>
       </template>
     </ul>
     ```

### How do you use event handlers?

You can use event handlers in vue similar to plain javascript. The method calls also support the special $event variable.
     ```javascript
     <button v-on:click="show('Welcome to VueJS world', $event)">
       Submit
     </button>

     methods: {
       show: function (message, event) {
         // now we have access to the native event
         if (event) event.preventDefault()
         console.log(message);
       }
     }
     ```

### What are the event modifiers provided by vue?

Normally, javascript provides `event.preventDefault() or event.stopPropagation()` inside event handlers. You can use methods provided by vue, but these methods are meant for data logic instead of dealing with DOM events. Vue provides below event modifiers for v-on and these modifiers are directive postfixes denoted by a dot.
     1. .stop
     2. .prevent
     3. .capture
     4. .self
     5. .once
     6. .passive
     
     Let's take an example of stop modifier,
     ```html
     <!-- the click event's propagation will be stopped -->
     <a v-on:click.stop="methodCall"></a>
     ```
     You can also chain modifiers as below,
     ```html
     <!-- modifiers can be chained -->
     <a v-on:click.stop.prevent="doThat"></a>
     ```

### What are key modifiers?
     
Vue supports key modifiers on `v-on` for handling keyboard events. Let's take an example of keyup event with enter keycode.
     ```html
     <!-- only call `vm.show()` when the `keyCode` is 13 -->
     <input v-on:keyup.13="show">
     ```
     Remembering all the key codes is really difficult. It supports the full list of key codes aliases
     1. .enter
     2. .tab
     3. .delete (captures both “Delete” and “Backspace” keys)
     4. .esc
     5. .space
     6. .up
     7. .down
     8. .left
     9. .right

     Now the above keyup code snippet can be written with aliases as follows,
     ```vue
     <input v-on:keyup.enter="submit" />
     <!-- OR with shorthand notation -->
     <input @keyup.enter="submit" />
     ```

     **Note:** The use of keyCode events is deprecated and may not be supported in new browsers.


### How do you define custom key modifier aliases?

You can define custom key modifier aliases via the global `config.keyCodes`. There are few guidelines for the properties
     1. You can't use camelCase. Instead you can use kebab-case with double quotation marks
     2. You can define multiple values in an array format
     ```javascript
     Vue.config.keyCodes = {
       f1: 112,
       "media-play-pause": 179,
       down: [40, 87]
     }
     ```

### What are the supported System Modifier Keys?

Vue supports below modifiers to trigger mouse or keyboard event listeners when the corresponding key is pressed,
     1. .ctrl
     2. .alt
     3. .shift
     4. .meta

     Lets take an example of control modifier with click event,
     ```vue
     <!-- Ctrl + Click -->
     <div @click.ctrl="doSomething">Do something</div>
     ```

### What are the supported Mouse Button Modifiers?

Vue supports below mouse button modifiers
     1. .left
     2. .right
     3. .middle

     For example, the usage of `.right` modifier as below
     ```vue
      <button
        v-if="button === 'right'"
        v-on:mousedown.right="increment"
        v-on:mousedown.left="decrement"
      />
     ```

### How do you implement two-way binding?

You can use the `v-model` directive to create two-way data bindings on form input, textarea, and select elements.

     Lets take an example of it using input component,
     ```vue
     <input v-model="message" placeholder="Enter input here">
     <p>The message is: {{ message }}</p>
     ```
     Remember, v-model will ignore the initial `value`, `checked` or `selected` attributes found on any form elements. So it always use the Vue instance data as the source of truth.


### What are the supported modifiers on model?

There are three modifiers supported for v-model directive.

     **1. lazy:** By default, v-model syncs the input with the data after each input event. You can add the lazy modifier to instead sync after change events.
     ```vue
     <!-- synced after "change" instead of "input" -->
     <input v-model.lazy="msg" >
     ```
     **2. number:** If you want user input to be automatically typecast as a number, you can add the number modifier to your v-model. Even with type="number", the value of HTML input elements always returns a string. So, this typecast modifier is required.
     ```vue
     <input v-model.number="age" type="number">
     ```
     **3. trim:** If you want whitespace from user input to be trimmed automatically, you can add the trim modifier to your v-model.
     ```vue
     <input v-model.trim="msg">
     ```

### What are components and give an example?
     
Components are reusable Vue instances with a name. They accept the same options as new Vue, such as data, computed, watch, methods, and lifecycle hooks(except few root-specific options like el).

     Lets take an example of counter component,
     ```javascript
     // Define a new component called button-counter
     Vue.component('button-counter', {
       template: '<button v-on:click="count++">You clicked me {{ count }} times.</button>'
       data: function () {
         return {
           count: 0
         }
       },
     })
     ```
     Let's use this component inside a root Vue instance created with new Vue
     ```javascript
     <div id="app">
       <button-counter></button-counter>
     </div>

     var vm = new Vue({ el: '#app' });
     ```

### What are props?

Props are custom attributes you can register on a component. When a value is passed to a prop attribute, it becomes a property on that component instance. You can pass those list of values as props option and use them as similar to data variables in template.
     ```javascript
     Vue.component('todo-item', {
       props: ['title'],
       template: '<h2>{{ title }}</h2>'
     })
     ```
     Once the props are registered, you can pass them as custom attributes.
     ```vue
     <todo-item title="Learn Vue conceptsnfirst"></todo-item>
     ```

### When component needs a single root element?

In VueJS 2.x, every component must have a single root element **when template has more than one element**. In this case, you need to wrap the elements with a parent element.
     ```vue
     <template>
        <div class="todo-item">
            <h2>{{ title }}</h2>
            <div v-html="content"></div>
        </div>
     </template>
     ```
     Otherwise there will an error throwing, saying that "Component template should contain exactly one root element...".

     Whereas in 3.x, components now can have multiple root nodes. This way of adding multiple root nodes is called as fragments.
     ```vue
     <template>
          <h2>{{ title }}</h2>
          <div v-html="content"></div>
     </template>
     ```

### How do you communicate from child to parent using events?

If you want child wants to communicate back up to the parent, then emit an event from child using `$emit` object to parent,
     ```javascript
     Vue.component('todo-item', {
       props: ['todo'],
       template: `
         <div class="todo-item">
           <h3>{{ todo.title }}</h3>
           <button v-on:click="$emit('increment-count', 1)">
             Add
           </button>
           <div v-html="todo.description"></div>
         </div>
       `
     })
     ```
     Now you can use this todo-item in parent component to access the count value.
     ```vue
     <ul v-for="todo in todos">
       <li>
         <todo-item
           v-bind:key="todo.id"
           v-bind:todo="todo"
           v-on:increment-count="total += 1"
         /></todo-item>
       </li>
     </ul>
     <span> Total todos count is {{total}}</span>
     ```

### How do you implement model on custom input components?

The custom events can also be used to create custom inputs that work with v-model. The `<input>` inside the component must follow below rules,

     1. Bind the value attribute to a value prop
     2. On input, emit its own custom input event with the new value.

     Let's take a custom-input component as an example,
        ```javascript
        Vue.component('custom-input', {
          props: ['value'],
          template: `
            <input
              v-bind:value="value"
              v-on:input="$emit('input', $event.target.value)"
            />
          `
        })
        ```
     Now you can use `v-model` with this component,
      ```vue
      <custom-input v-model="searchInput"></custom-input>
      ```

### What are slots?

Vue implements a content distribution API using the <slot> element to serve as distribution outlets for content created after the current Web Components spec draft.

     Let's create an alert component with slots for content insertion,
     ```javascript
     Vue.component('alert', {
       template: `
         <div class="alert-box">
           <strong>Error!</strong>
           <slot></slot>
         </div>
       `
     })
     ```
     Now you can insert dynamic content as below,
     ```vue
     <alert>
       There is an issue with in application.
     </alert>
     ```
