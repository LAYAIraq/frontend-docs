CourseNavItem 
===============
This component is used to render a single item in the course navigation editor.

## Structure

### Roots
- [`CourseNavChapter`](../course-nav)

### Dependencies
* `chapterFollowSet`from`@/mixins/general/course-chapters`
* `deepCopy`from`@/mixins/general/helpers`

### Components
- [`CourseNavPropertyEdit`](../course-nav)

### Mixins
* `courseNav`
* `locale`

Component Functionality
---------
### Props
- `courseEnd`: type: String, required: true
- `dragBubble`: type: Array, default set to [`false,false`]
- `dragEnd`: type: Array, default set to [`false,false`]
- `dragStart`: type: Boolean, default set to true
- `followingContent`: type: [`String,Array`] default set to null
- `value`: type: Object, required: true

### Data
- `collapsed `: set to true
- `moving`: set to false

### Computed Properties

#### VueX Getters
- `courseContent`
- `courseStart`

#### Local
- `followSet`: return `followingContent` either as an array or null.
- `item`: return `courseContent` getter based on the value's ID

### Watchers
- `dragBubble`
- `dragEnd`

### Lifecycle Events

### Methods
- `followHighlight`: emit highlight event when shift is pressed 
- `toggleCollapsed`: state of item, emit event to parent 
- `updateTitle`: commit title update to store 
