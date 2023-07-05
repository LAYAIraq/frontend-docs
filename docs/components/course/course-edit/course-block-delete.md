CourseBlockDelete
===============
This component provides tool to delete content block

## Structure

### Roots
* `CourseEditTools` 


### Dependencies
* `vuex`

### Mixins
* `locale`
* `routes`

Component Functionality
---------

### Computed Properties
#### VueX Getters
- `courseContent`

#### Local
- `contentToDisplay`: return current content block 

### Methods
- `delContent`: remove current content block in store
