CourseEditHeader
===============
This component provides navigation buttons on top of edit tools 

## Structure

### Roots
* `CourseEdit`

### Dependencies
* `kebabToCamel`from `@/mixins/general/helpers`
* `vuex`

### Mixins
* `locale`
* `routes`

Component Functionality
---------

### Computed Properties
#### VueX Getters
- `courseContent`
- `courseContentIdRouteMap`

#### Local
- `checkEmpty`: returns true if no content in course 

### Methods
- `typeName`: returns name of content block 
