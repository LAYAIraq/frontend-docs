CourseList
===============
This component is to wrap course list and for adding courses. 

## Structure

### Dependencies
* `util`from `../../../mixins/general/helpers.ts`

### Components
- `CourseCreate`
- `CourseListDetails`: not lazily loaded b/c always visible 

### Mixins
* `locale`

Component Functionality
---------

### Data
- `courses`: empty array
- `search`: empty string 

### Computed Properties
#### VueX Getters
- `courseList`
- `isAuthor`

### Lifecycle Events

#### created
- call `this.fetchCourses`

### Methods
- `fetchCourses`: dispatch vuex action "courseListFetch"
...
