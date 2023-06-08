Header
===============

This component shows the navbar

## Structure


### Dependencies
- vuex
- `ìcons` from `@/options/langs.js`

### Components
- `HeaderNotifications`from `@/components/notifications/header-notifications.vue` (Lazy Load)

### Mixins
- locale
### VueX Store Modules
- authentication
- profile
- role

Component Functionality
---------

#### VueX State
- `auth`

#### VueX Getters
- `isAdmin`
- `isEditor`
- `profileLanguage`
- `userId`
- `userOnline`

### Methods
- `checkCourse`: check if the route exists
- `getLocale`: get Browser Locale for localization
- `logout`:  remove local storage, redirect to login page
- `marginClass`: returns class for side margin depending on the language
- `setLang`: set a new user language

### Watchers
- `$route`: `checkCourse`

### Lifecycle Events

#### mounted
- call `checkCourse`
- call `$forceUpdate`
- call `getLocale`