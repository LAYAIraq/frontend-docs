AdminPanel
===============

This component manages users, assigns roles, changes email addresses, fires pw and changes request .

## Structure

### Dependencies

- `roles` from `@/options/roles`

### Components

### Mixins
- `locale`

### VueX Store Modules

Component Functionality
---------

### Computed Properties
#### VueX Getters
- `isAdmin`
- `userId`
- `users`

#### Local
- `assignableRoles`: returns roles barring admin to prevent having multiple admins accidentally
- `duplicateErrMsg`: returns error message for duplicate property
- `filteredList`: filters list according to regexes array
- `noEmailFormat`: returns true if string doesn't contain a stop or @
- `noRoleChosen`: true if role for new user is null or `null`
- `pageList`: split list into pages
- `regexes`: returns an array of regexes for filtering

### Methods
- `capitalizeFirstLetter`: returns string with capitalized first letter
- `changeUserRole`: send user role change to store 
- `createUser`: dispatch create user to store 
- `deleteUser`: dispatch delete user to store 
- `editUserEmail`: change user's email address
- `getUserList`: fetch user list if not present in store 
- `handleCreateUser`: prevent modal from closing if inputs are empty 
- `openModal`: set changingUserId, open modal with id `type`
- `relocateNonAdmin`: return to start page when user is not admin
- `resetUserPassword`: reset user's password
- `setFilter`: set filter data prop 
  ...

### Watchers
- `filter`: reset regexes when filter changes
- `filteredList`: repage list if filters change
- `pageSize`: repage list if page size changes 

### Lifecycle Events

#### created
-call `relocateNonAdmin`: return to start page when user is not admin Author
-call `getUserList`: fetch user list if not present in store Author
-set `pageList`: display 25 items per page
