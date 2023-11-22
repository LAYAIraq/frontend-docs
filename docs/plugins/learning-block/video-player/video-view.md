VideoView
===============
This component is to view Plyr content block

## Structure

### Dependencies
* `@/assets/styles/flaggables.css`
* `Plyr` from `plyr`
* `plyr/dist/plyr.css`

### Components
* [`FlagIcon`](../../course/flag/flag-icon)

### Mixins
* `locale`
* `pluginView`

Component Functionality
---------
### Data
- return object `this.viewData`

### Computed Properties
#### VueX Getters
- `courseContent`
- `courseSimple`

### Lifecycle Events
#### mounted
-  `this.initPlyr` 

### Methods
- `initPlyr`: initialize Plyr instance  
