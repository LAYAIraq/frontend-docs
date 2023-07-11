App
===============

This is the root component of LAYA. It sets some global styles, handles authentication, routes and mounts other components.

## Structure


### Dependencies

- open-dyslexic-regular.css from `open-dyslexic`
- @/styles/fonts.css
- @/styles/color-correction.css
- `publicRoutes` from @/router

### Components

- [`header`](../components/general/header)
- [`footer`](../components/general/footer)

### VueX Store Modules

- `profile`

Component Functionality
---------

### Computed Properties
#### VueX Getters

- `profileLang`
- `fontOptions`

### Methods
- `getClasses`: return global css classes for font and reading direction
- `getReadingDir`: return class name depending on locale
- `relocateUnauthorized`: relocate users that are not authenticated
- `restoreAuth`:  restore authentication from local storage, set vuex store

### Watchers
- `$route`: calls `relocateUnauthorized`

### Lifecycle Events

#### Created
- sets document title
- calls `restoreAuth` and `relocateUnauthorized`
