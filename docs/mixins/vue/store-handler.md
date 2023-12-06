StoreHandler                   
===============
This component contains methods to use store in components 

## Structure

### Methods
- `courseFetch`: get course from database and put in store, start other functions if successful   
- `enrollmentFetch`: load enrollment status of user 
- `enrollmentUpdate`: update enrollment in store  
- `flagsFetch`: Fetch flags for course from vuex
- `flagsUpdate`: persist flag state in database 
- `notificationsFetch`: get notifications newer than newest in store
- `notificationsMarkRead`: set notificationsReadAll commit in store 
