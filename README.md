## quick-vue-research
<br/>This is documenting the quick glance at the project writing the info so that I know the things learned.
<br/>This project will also contain the plans for implementing the project.

Order of files for project evaluation:
0) there are no tests ... "ok, to do ... write a few integration tests." 1) install jest 2) hook up jest 3) test command 4) write test.
0) package.json - no entry point found.
notable packages: vuedraggable, vue-notification, vee-validate, [underscore](https://github.com/HKskn/vue-underscore), uniqid, moment, font-awesome, [bulma-extensions](https://wikiki.github.io/)
1) public/index.html
2) src/main.js router and store added to vue instance (vuex found), App is rendered. custom components are registered.
3) src/router.js "window.Router",  history setup for project, title is added and classes removed if found. Vue.prototype.$ROUTES = Constants; is set.
4) src/routes/index.js and constants.js shows the routes.
5) src/App.js
6) look at vue.config.js for the webpack config.
```
                // allow import cycles that include an asyncronous import,
                // e.g. via import(/* webpackMode: "weak" */ './file.js')
                allowAsyncCycles : false,
```
7) 

https://vuejs.org/v2/cookbook/adding-instance-properties.html
-- begin link notes
Vue Instance Properties
```
$ is a convention Vue uses for properties that are available to all instances. 
This avoids conflicts with any defined data, computed properties, or methods.
```
We scope instance properties with $ to avoid being overridden by local variables.

```
Alias axios to Vue.prototype.$http:
Vue.prototype.$http = axios
```

```
you can easily organize shared code into modules, 
then require/import those modules wherever they’re needed. 

This is the epitome of explicitness, 
because in each file you gain a list of dependencies. 
You know exactly where each one came from.
```

-- end link notes
-- quick assignment note:
Register components
```
// Register Custom Elements
Vue.component('loading', Loading);
```
Once a component has been registered lets say in main.js then it can be called in a future component.
This is similar to adding Vue.prototype to register a variable.
-- end quick assignment note

-- begin css note
"bulma": "^0.7.2",
actual version downloaded "bulma": "0.7.5",
bulma cdn link for quick definition searches: https://cdnjs.cloudflare.com/ajax/libs/bulma/0.7.5/css/bulma.css
customize your bulma inside _theme.css
-- end css note

-- begin app.vue 
investigating meta, $route comes from route file where no current layout is specified in the meta object. lets add the layout. 👍
```
console.log(this.$route)
this.$route.meta && this.$route.meta.layout && console.log(this.$route.meta.layout)
```
-- end app.vue 

```
You could try using dynamic components.

Basically you change which component is being rendered depending on your route.

So it would probably be something like this:

<component v-bind:is="headerComponent"></component>
```

Vue cookbook:<br/>
<br/>(discussed earlier): [vue instance properties](https://vuejs.org/v2/cookbook/adding-instance-properties.html)
<br/>[form validation](https://vuejs.org/v2/cookbook/form-validation.html)
<br/>[relating to svg's](https://vuejs.org/v2/cookbook/editable-svg-icons.html)
<br/>[relating to unit tests](https://vuejs.org/v2/cookbook/unit-testing-vue-components.html)
<br/>[vue directive for custom code](https://vuejs.org/v2/cookbook/creating-custom-scroll-directives.html)
<br/>[lifecycle methods for memory leaks](https://vuejs.org/v2/cookbook/avoiding-memory-leaks.html)
<br/>[localStorage.setItem('cats', parsed)](https://vuejs.org/v2/cookbook/client-side-storage.html)
<br/>[publish those components, yo 😎](https://vuejs.org/v2/cookbook/packaging-sfc-for-npm.html)
<br/>[scope your slots? i.e. google maps](https://vuejs.org/v2/cookbook/practical-use-of-scoped-slots.html)

## Time check, just hit the 1hour mark.
