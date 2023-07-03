CourseHeader
===============

This component is used to display the header of the course detail page. ut displays the course title, the breadcrumb and the title of the content to display. 

## Structure

### Dependencies
* `slugify`,`unslugify` from `@/mixins/general/course-structure`

### Mixins
* locale

Component Functionality
---------

### Props
- `contentTitle`: it expects an object to be passed 
- `courseName`: expects a string to be passed
- `coursePath`: expects a string to be passed

### Computed Properties
- `subchapters`: returns subchapter slugs of the current coursePath 

#### VueX Getters
- `courseChapterNames`
- `courseSimple`

### Methods
- `chapterName`: returns the name of the chapter to display the breadcrumb, using lookup in courseChapterName if available, otherwise unslugifying the chapter name. 
