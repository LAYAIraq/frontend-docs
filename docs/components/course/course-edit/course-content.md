CourseContent 
===============
This component wraps components needed for content editing in a course. It provides a container or layout for these components. 

## Structure
### Dependencies
* `CourseFiles`from `@/components/course/course-edit/course-files.vue` 
* `stripKey`: from `@/mixins/general/helpers`
* `vuex`

### Components
- `CourseFiles`

### Mixins
* `locale`
* `routes`

Component Functionality
---------

### Props
- `type`: a string type with a default value of an empty string
- `saveChanges`: a boolean type with a default value of false.

### Data
- `preview`: is initialized with a boolean value of false.

### Computed Properties
#### VueX Getters

- `courseContent`: 

#### Local
- `cid`: returns the type of content
- `comps`: return create, edit, view components for given content type
- `editContent`: returns true if it's editing an existing content 
- `stepData`: return input data for content 

### Watchers
- `saveChange`:is set to true, it calls the "save" method to save the edited content.

### Lifecycle Events
#### mounted
- `!this.cid && !this.content`:called when the component is mounted and checks if the necessary data has been passed to the component. If the data is missing, it navigates back to the previous page using the Vue Router's "back" method.

#### beforeDestroy
- `this.editContent`:calls the "save" method and dispatches an action to update the course

### Methods
- `save`: to write changes made to the content to the store 

