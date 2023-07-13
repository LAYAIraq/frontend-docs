AuthorApplication
===============
Author Application modal for profile 

## Structure

### Dependencies

- `roles` from `@/options/roles`

### Components

### Mixins
- `locale`

### VueX Store Modules

Component Functionality
---------
### Data
- `applicationEdited`: `-1` increments once data is loaded from store
- `applicationNew`: a boolean value set to false
- `fullName`: a string value initialized to an empty string.
- `institution`: a string value initialized to an empty string.
- `formInput`: an object with two properties:
- `applicationText`: a string value initialized to an empty string.
- `areaOfExpertise`: a string value initialized to an empty string.

### Computed Properties
#### VueX Actions
- `userApplicationCreate`
- `userApplicationDecide`
- `userApplicationFetch`
- `userApplicationUpdate`

#### VueX Getters
- `isAuthor`
- `profile`
- `userApplication`

#### VueX Mutations 
- `applicationAdd`
- `applicationDecide`
- `applicationEdit`

### Methods
- `applicationSave`: save edits tp application in store
- `applicationSubmit`: depending on if application existed before, update existing or send new application, to be called onDestoy
- `applicationUserSet`: set mutable application parts, fetch application if none present
- `applicationWithdraw`: withdraw application, save in store


### Watchers
- `formInput`: watch for changes on form input 
- `userApplication`: mirror changes in store for render (e.g. when new application is set)

### Lifecycle Events

#### created
- call `applicationUserSet`: sets the user data for the application.

#### beforeDestroy
- call `applicationSubmit`