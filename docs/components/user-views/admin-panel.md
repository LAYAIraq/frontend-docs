AdminPanel
===============

## Structure

### Dependencies
- `roles` from `@/options/roles`
- vuex

### Mixins
- locale

Component Functionality
---------
### Data
- `createUserEmail`: string for email of user to create
- `createUserName`: string for name of user to create
- `createUserRole`: string for role of user to create, selected from `roles`
- `changeEmail`: string to change an exisitng user's email
- `changeRole`: string to change an exisiting user's role. selected from `roles`
- `changingUserId`: number, id of user whose data is to be changed
- `duplicateProperty`: string, used to render `duplicateErrMsg`
- `emailFilter`: string, used to filter emails in list
- `emptyCreateInput`: boolean, used to render error message at empty create
- `filter`: string to set filter
- `listPages`: array that reflects the paged view of the data
- `pageSelected`: number of the page currently selected, i.e. index of `listPages`, initially set to 0
- `pageSize`: number of items per page, intially set to 25
- `pageOptions`: array of `{ value, text }` objects for dropdown
- `regexArr`: array of regexes used to filter the list
- `roleFilter`: string, used to filter list by role
- `usernameFilter`: string, used to filter list by username


### Computed Properties
- `assignableRoles`: return `roles` barring admin to prevent having multiple admins accidentally
- `duplicateErrMsg`: returns error message for duplicate property in locale
- `filteredList`: filters list according to regexes array
- `noEmailFormat`: returns true if string doesn't contain a stop or @
- `noRoleChosen`: true if role for new user is null or 'null'
- `pagedList`: split list into pages, getter returns `listPages`, setter sets `listPages` by slicing `filteredList` according to given value
- `regexes`: getter returns `regexArr`, setter sets `regexArr` to array of regexes depending on which filters are set

#### VueX Getters
- `isAdmin`
- `userId`
- `users`

### Watchers
- `filter`: reset regexes when filter changes
- `filteredList`: repage list if filters change
- `pageSize`: repage list if page size changes

### Methods
- `capitalizeFirstLetter`: returns string with capitalized first letter
- `changeUserRole`: send user role change to store
- `createUser`: dispatch create user to store
- `deleteUser`: dispatch delete user to store
- `editUserEmail`: change user's email address
- `getUserList`: fetch user list if not present in store
- `handleCreateUser`: prevent modal from closing if inputs are empty, email has wrong format, fire `createUser` when not
- `openModal`: set `changingUserId`, open modal with id `type`
- `relocateNonAdmin`: return to start page when user is not admin
- `resetUserPassword`: reset user's password
- `setFilter`: set filter data prop


### Lifecycle Events

### created
- call `relocateNonAdmin` to relocate non-admin users
- call `getUserList` to retrieve a list of users
- set `pagedList` to 25 users per page
