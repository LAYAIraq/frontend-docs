CourseEdit   
===============
This store module is to edit course content and especially course navigation.

## Dependencies
- `http` from `axios`
- `v4 as uuid4` from `uuid`
- `slugify` from `@/mixins/general/slugs`
- `LegacyContentBlock` from `@/mixins/types/course-structure`

## State
- `course`: An empty object.
- `courseUpdated`: set to false 

## Getters
### content 
The provided getter returns the content Array of a given `state`course.  

### course
This getter returns the course object from the state. It provides a way to access the full course data in any component.

### courseCreator 
This getter extracts and returns the userId of the creator from the course data stored in the Vuex state. It provides a clean way to access just the creator ID from any component.

### courseId
This getter extracts and returns the `courseId` string value from the course data stored in the Vuex state. It provides a clean way to access just the `courseId` from any component.

### courseLanguage 
This getter returns the course language string value stored in the course data in the Vuex state. It provides a clean way to access just the course language from any component.

### courseSimple 
This getter returns the value of the `simpleLanguage` flag from the course properties stored in state. It provides a clean way to check the course simple mode setting from any component.

### courseSlug
This getter takes the course name from state, runs it through the slugify utility and returns the processed slug. It generates a clean slug version of the course name that can be used when accessing the course data.

### courseStorage 
This getter returns the storage ID from the course data stored in the Vuex state. It provides a clean way to access just the course storage ID from any component.

### courseUpdated 
This getter

## Mutations
### courseAbstractChange
Updates the course abstract by setting the new value.

### courseAuthorNameChange
Updates the course author name by setting the new value.

### courseCategoryChange
Updates the course category by setting the new value.

### courseLanguageChange
Updates the course language by setting the new value.

### courseKeywordsChange
Updates the course keywords by setting the new value.

### coursePropertiesChange
Updates the course properties object by merging the new properties.

### coursePropertyCheck
Checks all course blocks and sets text/video properties accordingly.

### courseRename
Renames the course by setting the new name value.

### courseSet
Sets the entire course object to the passed data.

### courseSimpleLanguageCheck
Checks all blocks for simple language and sets simple property.

### courseUpdatedSet
Sets the courseUpdated flag to the passed value.

## Actions
### courseCreate
Creates a storage, then creates the course in the backend.

### courseCopy
Copies an existing course, including files. TODO: not working for files.

### courseDelete
Deletes a course by ID, storage, and files.

### courseFetch
Loads a course from backend by ID/name into state.

### courseUpdate
Updates course data and files in backend database.

### courseUpdateLanguage
Patches the course language value in backend.

### courseUpdateRename
Patches the course name value in backend.
