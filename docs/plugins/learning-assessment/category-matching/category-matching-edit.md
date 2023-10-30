Category Matching Edit
===============
This component is to edit or create category matching assessment. Allows instructors to manage category matching blocks for assessments.

## Structure

### Dependencies
* `deepCopy`from `@/mixins/general/helpers`
* `v4 as uuidv4`from`uuid`

### Mixins
* `array`
* `locale`
* `pluginEdit`
* `routes`
* `tooltipIcon`

Component Functionality
---------

### Data
- `categories`:an array to store categories
- `id`:initially set to null
- `items`:an array to store items
- `taskAudio`:an object representing the task audio
- `task`:an object representing the task
- `title`:an object representing the title

### Computed Properties
#### VueX Getters
- `courseContent`
- `courseSimple`

### Lifecycle Events

#### created
- If in `edit` mode, call `fetchesData`
- If not in `edit` mode, call `fillsForm`
- call `taskTitlePopulate`

### Methods
- `fetchData`:fetch data from vuex and make data property 
- `fillForm`:fill item and category props with localized tokens
- `newItem`: creat a new object for items 