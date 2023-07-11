Course
===============

Show Course Content 

## Structure

### Dependencies
* `utils` from `@/mixins/general/helpers.ts`

### Components
- `lyScrollToTop`:lazy loaded 
- `CourseEdit`: lazy loaded
- `CourseHeader`

### Mixins

* `locale`
* `routes`
* `storeHandler`

Component Functionality
---------

### Computed Properties
- `beforeRouteUpdate`: checks if the to route has a name of `course` and if the form route does not have a name of `course-content` or `course-nav`. If this condition is true, it means that the user is navigating to the `course` route from a different route, and not from the `course-content` or `course-nav` routes.

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
- `followContent`: returns the result of calling `followingContent` with an argument `contentToDisplay`.
- `viewPermit`: returns true if user is allowed to see selected course 

### Watchers
- `courseFlags`: update when courseFlags change

### Lifecycle Events

#### created
- call `getCourse`
- call `enrollmentFetch`

### Methods
- `getCourse`: get course from backend, set title
- `followingContent`: returns follow set for content block
