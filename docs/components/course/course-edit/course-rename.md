CourseRename
===============
This component is to rename the whole course 
## Structure

### Roots
* `CourseEditTools`

### Mixins
* `locale`

Component Functionality
---------

### Data
- `dupeName`: set to false
- `noName`: set to false
- `oldName`: empty string 
- `rename`: empty string 

### Computed Properties
#### VueX Getters
- `course`
- `courseList`

#### Local
- `renameOk`: prüft, ob eine Umbenennung des Kurses durch den Benutzer möglich ist oder nicht

### Watchers
- `noName`
- `rename`

### Methods
- `duplicateCheck`: check if rename already exists, call renameCourse() if it doesn't 
- `handleOk`: trigger validation of rename 
- `renameCourse`: rename Course, change route to a new name 
