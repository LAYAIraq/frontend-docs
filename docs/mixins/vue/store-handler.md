StoreHandler                   
===============
This mixin contains methods to use store in components 

## Structure

### Methods
- `courseFetch`: fetches a course by name, updates enrollment data, sets the courseUpdated flag, and handles potential errors.  
- `enrollmentFetch`: checks if the course has an `enrollment` property, and if so, it dispatches the `enrollmentFetch` action in the store with the courseId to fetch the enrollment data.
- `enrollmentUpdate`: dispatches the `enrollmentUpdate` action in the store to update the enrollment status.  
- `flagsFetch`: dispatches the `courseFlagsFetch` action in the store with the courseId to fetch course flags.
- `flagsUpdate`: dispatches the `courseFlagsUpdate` action in the store to update course flags.
- `notificationsFetch`: triggers the `notificationsFetchNew` action in the store to retrieve new notifications.
- `notificationsMarkRead`: set `notificationsReadAll` commit in store 
