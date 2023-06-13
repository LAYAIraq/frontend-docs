Notifications
===============

This component organizes Notifications for Users
## Structure

### Dependencies
- `http` from `axios`


### Mixins
- locale
- storeHandler
- time

Component Functionality
---------
### Computed Properties
- `moreMessages`: return true if more notifications can be loaded

#### VueX Getters
- `notifications`
- `unreadMessages`

#### VueX State
- `message`

### Methods
- `cacheValues`: get all referencing data for notifications, set loading to false if done
- `linkToCourse`: return link to referred course id
- `getReference`: get course name for id (async?)
- `highLightMessage`: scroll highlighted message into view
- `loadMoreNotifications`: get more notifications from database
- `markAsRead`: set 'read' boolean in message's data
- `noteTime`: return timestamp in locale
- `replaceStr`: replace placeholder in notification text with referenced value

### Lifecycle Events

### created
- call `$store.dispatch('notificationsFetchInitial)` to fetch the first notifications
- call `cacheValues`: to performs some initial setup
#### mounted
- set up watcher for `collapse` event to update `read` property for single notifications
#### beforeDestroy
- it dispatches `notificationsUpdateRead`, updating the `read` property of notifications in database
