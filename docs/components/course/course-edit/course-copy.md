CourseCopy
===============
This component provides tools for copying a course 

## Structure

### Roots
* `CourseEditTools`

### Dependencies
* `http`from `axios`
* `vuex`

### Mixins
* `locale`

Component Functionality
---------
### Data
- `copy`: is initialized as an empty string to store a copy of some data

### Computed Properties
#### VueX Getters
- `course`

### Methods
- `copyCourse`: copy course if no course with that name already exists 
