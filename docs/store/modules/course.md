Course  
===============

This store manages course-related data and includes an action to fetch a course from the backend server and update the course structure.
## Dependencies
- `Course` from `@/mixins/types/course-structure`
- `http` from `axios`

## Actions
### courseFetch
The function retrieves a course from a backend server, calls the `courseStructureDestructure` mutation, and returns a promise with the response data.
