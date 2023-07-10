CourseBlockNew
===============
This component creates a new content block.

## Structure

### Roots
* `CourseEditTools`

### Dependencies
* `kebabToCamel`, `stripkey`from `@/mixins/general/helpers`
* `vuex` 

### Mixins
* `locale`
* `routes`

Component Functionality
---------

### Computed Properties
#### VueX Getters
- `course`

#### Local
- `organization`: return course organization blocks, without feedback if course has no enrollment

### Methods
- `getCaption`: get caption property of $laya block
- `getName`: get name property of $laya block
