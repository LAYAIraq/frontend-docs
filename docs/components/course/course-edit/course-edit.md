CourseEdit
===============
This component wraps all course edit tools.

## Structure

#### Components
- `CourseEditHeader`: lazy loaded
- `CourseEditTools`: lazy loaded 

### Mixins
* `locale`
* `routes`

Component Functionality
---------

### Data
- `changeToSave`: is initialized with a boolean value of false to track whether there are any changes that need to be saved.

#### Methods
- `storeCourse`: dispatch the courseUpdate store action, showing a toast if it resolves. 
