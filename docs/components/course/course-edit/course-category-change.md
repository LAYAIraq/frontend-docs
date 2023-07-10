CourseCategoryChange
===============

This component is used to change the category of a course.

## Structure

### Roots
* `CourseEditTools`

### Dependencies
* `vuex`

### Mixins
* `locale`

Component Functionality
---------

### Data
- `badInput`: is set to null to track whether the user has entered invalid input
- `newCategory`:  is initialized as an empty string to store the user's input for the new category.

### Computed Properties
#### VueX Getters
- `course`

#### Local
- `inputWarning`: returns a string value, which is either the localized error message corresponding to the "badInput" property, or a default message if "badInput" is null or undefined. This computed property displays a warning message to the user if they entered invalid input.

### Methods
- `changeCourseCategory`: change course category
