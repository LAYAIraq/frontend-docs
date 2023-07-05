Course
===============

Show Course Content 

## Structure

### Dependencies
* `utils` from `@/mixins/general/helpers.ts`
* `CourseHeader` from `@/components/course/course-header.vue`
* `vuex`

### Components
- `lyScrollToTop`from `@/components/helpers/scroll-to-top.vue`
- `CourseEdit` from `@/components/course/course-edit/course-edit.vue`
- `CourseHeader`

### Mixins

* `locale`
* `routes`
* `storeHandler`

Component Functionality
---------

### Computed Properties
- `beforeRouteUpdate`: checks if the to route has a name of 'course' and if the form route does not have a name of 'course-content' or 'course-nav'. If this condition is true, it means that the user is navigating to the 'course' route from a different route, and not from the 'course-content' or 'course-nav' routes.

#### VueX Getters

- `content`
- `course`
- `courseChapterNames`
- `courseContent`
- `courseContentIdRouteMap`
- `courseContentIndexIdMap`
- `courseContentRouteIdMap`
- `courseFlags`
- `courseNav`
- `courseRoutes`
- `courseSlug`
- `enrollment`
- `isAdmin`
- `isAuthor`
- `storeBusy`
- `userEnrolled`
- `userId`

#### Local
- `isCourseAuthor`: return true if logged user is admin or author of the course
- `onFinishDummy`: returns empty function on every [] invocation, is used as a fallback when a real function is not available.
- `contentToDisplay`: return current content object
- `viewPermit`: returns true if user is allowed to see selected course 

### Lifecycle Events

#### created
- call `getCourse`
- call `enrollmentFetch`

### Watchers
- `courseFlags`: update when courseFlags change

### Methods
- `getCourse`: get course from backend, set title
- `followingContent`: returns follow set for content block ?(followingContent not followContent?)
