CourseNavFollowEdit
===============
This component is used to display the follow edit view of a course nav item.

## Structure

### Components
- [`SuggestingInput`](../course-nav)

### Mixins
* `array`
* `locale`
* `routes`

Component Functionality
---------
### Props
- `contentId`: type: String, required: true
- `follow`: type: Array, default: null

### Data
- `followSetNew`: initialized with a copy of the follow array using the slice()

### Computed Properties
#### VueX Getters
- `courseContent`

#### Local
- `buttonLabels`: return text of buttons if item is button navigation 
- `followSetChange`: return if follow set has been changed 
- `followSetComplete`: returns true if follow set is complete, i.e. has no null values 

### Lifecycle Events

### Methods
- `followEdit`: modify followSetNew array as reactivity is intact 
- `saveFollow`: check if follow set is complete, then store it  
