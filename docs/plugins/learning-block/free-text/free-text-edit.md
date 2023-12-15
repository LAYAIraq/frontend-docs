FreeTextEdit 
===============
This component is edit free content block

## Structure

### Dependencies
* `Quill`from`quill`

### Components
* [`ContentTitleEidt`](../../helpers/content-title-edit)

### Mixins
* `locale`
* `pluginEdit`
* `routes`
* `tooltipIcon`

Component Functionality
---------
### Data
- `contents`: set to null
- `title`: an empty object  

### Computed Properties
#### VueX Getters
- `courseContent`
- `courseSimple`

### Lifecycle Events
#### created
- checks `this.edit` is in edit mode.
- calls `this.fetchData` method if in edit mode.
- else calls `this.taskTitlePopulate` method.

#### mounted
- call `initQull`
   
### Methods
- `fetchData`: fetch data from vuex and make data property  
- `initQuill`: initialize wysiwyg editor