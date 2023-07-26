Flag
===============
This component is to display flag view 

## Structure

### Components
- `FlagAnswer`
- `FlagQuestion`


### Mixins
* `locale`
* `storeHandler`

Component Functionality
---------
### Data
- return `flag`: set to null

### Computed Properties
#### VueX Getters

- `course`
- `courseId`
- `courseFlags`

### Watchers
- `courseFlags`: deep watcher to update currentFlag

### Lifecycle Events

#### created
- `!this.courseId` `this.courseFetch`: executes when the component is created. Fetches data for the course and updates the flag property.
