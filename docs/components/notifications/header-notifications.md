HeaderNotifications
===============

## Structure

### Mixins
- locale
- storeHandler
- time

Component Functionality
---------

### Data
- `notifyShortList`: array to show the most recent notifications

### Computed Properties
- `messagesPresent`: return true if there are notifications

#### VueX Getters
- `notifications`
- `notificationsUnreadNumber`
- `userId`


### Methods
- `setShortList`: take first 5 elements of notifications for dropdown

### Watchers
- call `notifications`

### Lifecycle Events

### created
- calls `$store.dispatch('notificationsFetchInitial)`, fetching notifications for user
- calls `setShortList`, filter the initial notifications data fetched in the previous step to create a smaller list of the relevant notifications for the user.

#### mounted
-`beforeDestroy`: it dispatches "notificationsUpdateRead" to the Vuex store using the $store object.