CourseNavigationEditor
===============
This component provides a file wrap course navigation editor.
## Structure

### Dependencies
+ `courseContentIdGet`from`@/mixins/general/course-structure`
* `deepCopy`, `stripKey`from`@/mixins/general/helpers`
* `slugify`from`@/mixins/general/slugs`
* `v4 as uuidv4`from`uuid`

### Components
- [`CourseNavChapter`](../accessibility-settings)

### Mixins
* `locale`
* `tooltipIcon`

Component Functionality
---------
### Data
- `chapterNamesDuplicate`: boolean state set to`false`
- `chaptersCoherent`: empty object
- `chaptersDuplicate`: empty object
- `chaptersIncoherent`: boolean state set to`false`
- `courseNavEdit`: empty array
- `edited`: boolean state set to`false`
- `previewId`: empty placeholder
- `preview`: boolean state set to`false`

### Computed Properties

#### VueX Getters
- `courseChapters`
- `courseContent`

#### Local
- `courseEnd`: returns the ID of the last chapter
- `messageShow`: returns a boolean value indicating whether there have been any edits
- `previewComponent`: retrieves the necessary components from various sources
- `previewData`: retrieves the preview data from the `courseContent` using the `previewId`

### Watchers
- `chaptersCoherent`: checks and retrieves the coherence status of chapters.
- `chaptersDuplicate`: checks and retrieves the duplicate chapter names status.
- `courseChapters`: retrieves a deep copy of the course chapters and assigns it to `courseNavEdit`.

### Lifecycle Events

#### created
- initializes the `courseNavEdit` property, when chapters empty, create them

### Methods
- `chapterAdd`: function Add chapter object to `courseNavEdit` data prop
- `chapterDelete`: update chapter map if chapter was deleted
- `chaptersCoherentUpdate`: update chaptersCoherent to monitor integrity of sub-chapters
- `chaptersCreate`: create courseNav from course chapters if none in store, returns {{children: *[], isChapter: boolean}} courseNav data structure
- `chaptersDuplicateUpdate`: update chaptersDuplicate object to monitor chapter names
- `integrityCheck`: check if chapter names are duplicate or chapters incoherent, show modal if yes
- `navigationSave`: write changed nav into store, emit saved event to trigger persistence
- `previewClear`: set preview variables to default 
- `previewSet`: set preview boolean true, `previewId` to param value. Param `pid`id of content to preview 
- `propertyChange`: change chapter name of referenced chapter object. 
