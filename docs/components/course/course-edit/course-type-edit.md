CourseTypeEdit
===============
This component is to edit type of current content block 

### Roots
* `CourseEditTools`

### Dependencies
* `kebabToCamel`: from `@/mixins/general/helpers`

### Mixins
* `locale`
* `routes`

Component Functionality
---------

### Data
- `changetype`: set to null

### Computed Properties
#### VueX Getters
- `courseContent`

#### Local
- `contentToDisplay`: return current content block

### Watchers
- `plugins`: make localized names of Laya plugins available as computed property

### Methods
- `changeContentType`: change content type, remove all 

