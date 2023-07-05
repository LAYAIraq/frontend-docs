CourseHeader
===============

This component is used to display the header of the course detail page. ut displays the course title, the breadcrumb and the title of the content to display. 

## Structure

### Roots
* `course`

### Dependencies
* `slugify`,`unslugify` from `@/mixins/general/course-structure`

### Mixins
* `locale`

Component Functionality
---------

### Props
- `contentTitle`: required,it expects an object to be passed 
- `courseName`: required,expects a string to be passed
- `coursePath`: required,expects a string to be passed

### Computed Properties
#### VueX Getters
- `courseChapterNames`
- `courseSimple`

### Local 
- `subchapters`: returns subchapter slugs of the current coursePath

### Methods
- `chapterName`: returns the name of the chapter to display the breadcrumb, using lookup in courseChapterName if available, otherwise unslugifying the chapter name. 
