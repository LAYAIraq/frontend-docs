CourseEdit
===============
This component wraps all course edit tools.

## Structure

### Dependencies
* `CourseEditHeader`from `@/components/course/course-edit/course-edit-header.vue`
* `CourseEditTools` from `@/components/course/course-edit/course-edit-tools.vue`

### Components
- `CourseEditHeader`
- `CourseEditTools`

### Mixins
* `locale`
* `routes`

Component Functionality
---------

### Data
- `changeToSave`: is initialized with a boolean value of false to track whether there are any changes that need to be saved.

#### Methods
- `storeCourse`: store course in database
