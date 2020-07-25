# vue-template
a template or starting point you can say, for crafting vue js application.

Directory stracture

## assets
For static assets like images.

## components 
For global/generic/common components which will be available across the application. After creating a component you can add it to **components/index.js**. **Note** it
is only for global component.

## layouts
For layout files. Layout file must include **<child />** component. Which is a global component. Layouts can be included with layout: 'layoutName' .
Example: 

```node
// layouts/auth.vue

//in code 

<script>
export default {
  ...
  layout: 'auth'
}
</script>
```

## middlewares 
Basic middleware stuff.

## mixin
Basic vue mixing.

## modules
Modules is sort of a replica of a mini vue app. Containing pages, components, services, routes, state, api routes etc within. It has three bindings possibilites.

- **stores** Every module that interacts with state must expose a namespaced vuex store and registered in `/stores/index.js`.
- **api routes** Every module that interacts with the backend api must expose routes and must be registered in `/api_routes.
- **stores** Every module that has pages, meaning that has routes for the frontend, must expose a routes files compatible with vue router and must be registered in 
`/router/routes.js`.

example 

```node

modules/user
  ---------/store/index.js
                 /getters.js
                 /actions.js
  ----/services/userService.js
               /userSettingsService.js
  ----/pages/profile.vue
            /settings.vue
            /orders/index.vue
  ----/components/card/basic.vue
                /card/secondary.vue
  ---/api_routes.js
  ---/routes.js
  
modules/product
  ---------/store/index.js
  ----/services/userService.js
               /userSettingsService.js
  ----/pages/gallery.vue
            /single.vue
            /review/product.vue
  ----/components/card/slider.vue
  ---/routes.js
```

* Any module will implement according to its responsibilities.

## pages
Common pages like welcome/errors etc.

## packages
Packages are sort of like plugins but can be used globally or does not server any specific module. And can act independently.

## plugins 
Plugins are packages and 3rd party libraries but up for modifications. Like you can set the timezone for moment in this section. **Plugins are booted when the application boots**.

## router 
The main vue router. Allowed for modification as you wish.

## store
The main state manager. Allowed for modification as you wish.

## api_routes.js 
The glue of all the modules, for the [api-router](https://github.com/thearyanahmed/api-router)

## app.js
The main entry point. That binds everything.

## bootstrap.js 
Bootstraps the application.

## conf.js 
a config file.

## globals. 
For globaly functions. Will be deprecated.


