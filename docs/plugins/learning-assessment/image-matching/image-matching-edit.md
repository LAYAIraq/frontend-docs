ImageMatchingEdit 
===============
This component is to create or Edit an Image Matching Assessment block

## Structure

### Dependencies
* `deepCopy`from`@/mixins/general/helpers`
* `v4 as uuidv4`from`uuid`

### Components
* [`ContentTitleEidt`](../../helpers/content-title-edit)

### Mixins
* `array`
* `locale`
* `pluginEdit`
* `tooltipIcon`

Component Functionality
---------
### Data
- `pairs`: an empty array
- `relations`: an empty array 
- `taskAudio`: an empty string
- `task`: an object represents a task
- `title`: an object has the following properties:
  - `flagged`: boolean set to false
  - `id`: an empty string
  - `show`: boolean set to false
  - `text`: an empty string

### Lifecycle Events
#### created
-  initializes`this.edit`data and performs actions based on whether the component is in edit mode or not.
### Methods
- `fetchData`: fetch data from vuex and make data property  
- `fillForm`: fill form with default values  
- `newPair`: return pair with new id 
