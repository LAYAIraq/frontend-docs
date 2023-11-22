ButtonNavigationEdit 
===============
This component is edit Button Navigation content block

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
- `answers`: an empty array
- `by`: set empty string 
- `task`: an empty object 
- `title` an empty object
  
### Computed Properties
#### VueX Getters
- `courseContent`
- `courseSimple`

### Lifecycle Events
#### created
- checks `this.edit` is in edit mode.
- calls `this.fetchData` method if in edit mode.
- else execute `this.taskTitlePopulate` method.
- call `this._itemAdd(this.answers, this.newItem`: Adds a new item to the answers array.

### Methods
- `fetchData`: fetch data from vuex and make data property 
- `newItem`: return new item