CoursePreferences 
===============
This component shows preferences in Course Tools (e.g. enrollment requirements)

## Structure

### Roots
* `CourseEditTools`

### Mixins
* `locale`

Component Functionality
---------

### Data
- `enrollment`: set to false
- `simple`: set to false
- `simpleLanguage`: set to false

### Computed Properties
#### VueX Getters
- `course`
- `courseList`

### Lifecycle Events

#### created
- sets `this.enrollment` to `prefs.enrollment`
- sets `this.simpleLanguage` to `prefs.simpleLanguage`
- calls `this.checkForSimpleLanguage`

### Methods
- `changeSettings`: call store to persist preferences 
- `checkForSimpleLanguage`: check if children have simple language property that is not empty, set simple property accordingly
- `toggleEnrollment`: toggle enrollment boolean
- `toggleSimpleLang`: toggle simpleLanguage boolean