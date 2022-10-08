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
