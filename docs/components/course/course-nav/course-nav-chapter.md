CourseNavChapter
===============
This component is used to display the follow edit view of a course nav.
## Structure

### Roots
- [`CourseNavigationEditor`](...)

### Dependencies
* `Draggable`from`vuedraggable`
* `chapterFollowSet`from`@/mixins/general/course-chapters`
* `deepCopy`from`@/mixins/general/helpers`
* `v4 as uuidv4`from`uuid`

### Components
- [`CourseNavItem`](...)
- [`CourseNavPropertyEdit`](...)

### Mixins
* `courseNav`
* `locale`

Component Functionality
---------
### Props
- `chapterNameDuplicate`: type: Boolean, default set to false
- `chapterName`: type: String, default set to `chapterName`
- `chapter`: type: Object, required: true
- `courseEnd`: type: String, required: true
- `followingContent`: type: String, default set to null
- `highlightedBlock`: type: String, default set to null
- `main`: type: Boolean,default set to false

### Data
- `chapterNameChange `: set to false
- `childrenVisibility`: empty object
- `collapsed`: set to false
- `dragEndIndex`: set to null
- `dragStartIndex`: set to null
- `dragging`: set to false
- `highlightId`: set to null
- `id`: call `uuidv4`, exists to make v-for keys unique

### Computed Properties

#### Local
- `children`: returns the chapter children directly from data
- `coherentItem`: check if all children are coherent, i.e. either all are chapters or all are items, `Boolean`true if all children are coherent items
- `duplicateChapterName`: return a list of indexes of children with duplicate chapter names, `String`list of duplicate chapterNames indexes

### Watchers
- `chapter`: called on chapter change, emits edited event if main chapter, watches chapter deeply

### Lifecycle Events

#### created
- initializes `childrenVisibility` object, sets all children to invisible, emits coherence check on mount

#### Destroyed
- emits `deleted-chapter` event before destroy, passes chapter ID

### Methods
- `blockHighlightUnset`: unset highlighted id if main chapter
- `blockHighlight`: emit highLighted content's id if not main chapter, else set it
- `chapterDeleteUpdate`: remove chapter by name, adding their children to chapter, propagate changes 
- `chapterDelete`: propagate removal of a chapter 
- `childVisibilityChange`: set visibility of child in `childrenVisibility` object
- `coherenceEmit`: emit coherence status of chapter 
- `dragEnd`: handle event when drag ends, setting `dragEndIndex`and calling `followingContentSet`if main element 
- `dragStart`: handle event when drag starts, setting `dragStartIndex`and dragging to true
- `followingContentSet`: set `followingContent`property of all items in the chapter 
- `propagatePropertyChange`: propagate property change from child Component to parent 
