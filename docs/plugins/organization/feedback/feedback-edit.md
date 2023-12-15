FeedbackEdit 
===============
This component is to edit or create Course Feedback content block

## Structure

### Dependencies
* `deepCopy` from `@/mixins/general/helpers`
* `v4 as uuid4` from `uuid`

### Components
* [`ContentTitleEidt`](../../helpers/content-title-edit)

### Mixins
* `array`
* `locale`
* `pluginEdit`
* `routes`
* `tooltipIcon`

Component Functionality
---------
### Data
- `categories`: an empty array 
- `id`: set empty string 
- `items`: an empty array
- `taskAudio`: an empty string 
- `task`: an empty string  
- `title` an empty string 
  
### Computed Properties
#### VueX Getters
- `courseContent`
- `courseSimple`

### Lifecycle Events
#### created
- checks `this.edit` is in edit mode.
  - calls `this.fetchData` method if in edit mode.
- else call `this.fillForm` method.
  - call `this.taskTitlePopulate` method. 

### Methods
- `fetchData`: fill in localized sample input  
- `fillForm`: fill in sample input 
- `newItem`: return new item with empty text 