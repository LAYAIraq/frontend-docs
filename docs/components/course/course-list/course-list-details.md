CourseListDetails
===============
This component is to list all available courses, users can start or enroll

## Structure

### Roots
* `CourseList`

### Dependencies
* `slugify`from `@/mixins/general/course-structure`

### Mixins
* `locale`
* `storeHandler`

Component Functionality
---------
### Props
- `filter` defined with a type of `String`

### Data
- `buttonAction`: set to null, will be updated by user input
- `complicitCheck`: set to null, store data related to course enrollment.
- `complicitCourses`: set to null, store data related to course enrollment.
- `enrolledIn`: empty array, store a list of courses that the user has enrolled in. 
- `filteredList`: empty array, to store a list of courses that match a specific search or filter criteria.
- `nonComplicitSettings`: empty object, tore settings related to the user's enrollment status.
- `nonCompliicitList`: empty array, o store a list of courses that the user is not enrolled in.
- `selectedCourse`: empty string, store and manipulate data.  

### Computed Properties
#### VueX Getters

- `course`
- `courseList`
- `prerencesMedia`
- `userId`

#### Local
- `complicitReady`: returns true if complicit Set has any members
- `filtered`: filter course list depending on user input 

### Watchers
- `courseList` call `this.getComplicitCourses`: watch course list in order to have non-complicit indicator at first load

### Lifecycle Events

#### created
- call `this.getSubs`
- `this.filteredList` used to creat a copy of the `this.courseLust`
- call `this.getComplicitCourses` to update data

### Methods
- `decideButtonAction`: redirect to course or show modal depending on course status concerning media preferences 
- `getComplicitCourses`: check user's preferences and check if course complies to them, if not, remove from complicitCourses and add list to nonComplicitSettings 
- `getIcon`: return for icon corresponding to setting prop
- `getSubs`: get a list of all courses the user enrolled in
- `isEnrolled`: return false if course needs an enrollment and user is not enrolled, true if no enrollment needed or user is enrolled 
- `markAsNonComplicit`: add array in complicitSettings if not present for courseId, add property to array 
- `subscribe`: Lets user enroll in a course