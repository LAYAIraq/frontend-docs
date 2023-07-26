CourseCreate
===============
This component implements the form to add a new course 

## Structure

### Roots
* `CourseList`

### Mixins
* `locale`

Component Functionality
---------

### Data
- `duplicateNameCategory`: set to false
- `msg`: empty string
- `newCourse`{ `category`: empty string,`name`:empty string}
- `newCourseNeedsEncoding`: set to false 

### Computed Properties
#### VueX Getters
- `courseList`
- `userId`

#### Local
- `formValid`: to test if both name and category are set 
- `needsEnrollment`: check if new course will need an enrollment 

### Methods
- `checkNames`: check if name or category contain sensitive characters 
- `duplicateCheck`: check for duplicate keys before storing the course 
- `storeNewCourse`: check for duplicate name, persist new database entry, create a new storage 
- `trimNames`: remove whitespace from beginning and end of newCourse properties
