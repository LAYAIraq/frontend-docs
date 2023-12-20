CourseContent   
===============
This store module is to manage course content and especially course navigation.

## Dependencies
- `ContentBlcok`,
- `Course`,
- `CourseNavigationItem` from `@/mixins/types/course-structure`
- `courseContentIdGet`,
- `coursePathsGet`,
- `courseChaptersCollect`,
- `courseDestructure`,
- `legacyContentFollowTransform`,
- `legacyContentStepsTransform` from `@/mixins/general/course-structure`
- `stripKey` from `@/mixins/general/helpers`
- `v4 as uuidv4` from `uuid`
- `http`, `AxiosResponse`from `axios`
- `Vue` from `vue`
- `chaptersCheck`,
- `chaptersExtractFollow`,
- `chapterSlugDuplicateAvoid`,
- `chapterSlugUpdate` from `@/mixins/general/course-chapters`
- `slugify`from `@/mixins/general/slugs`

## State
- `courseContent`: An empty object used for storing course content data.
- `courseChapters`: An empty array used for storing course chapter data.
- `courseChapterNames`: An empty object used for storing course chapter names.
- `courseRoutes`: An empty array used for storing course route data.

## Getters

### courseChapter: 
The provided getter retrieves the value of the `courseChapters` property from the state object.

### courseChaptersCoherent
The getter calculates the coherence of the `courseChapters` property in the state object by calling the `chaptersCheck` function with a specific configuration.

### courseChapterNames
This getter collects the `courseChapters` property from the state object and returns it by calling the `courseChaptersCollect` function.

### courseContent
This getter retrieves the `courseContent` property from the state object and returns it directly.

### courseContentFollowMap
This getter initializes an empty object called map. It then calls the `chaptersExtractFollow` function with `state.courseChapters` and map as arguments to populate the map object. Finally, it returns the populated map object.

### courseContentIdRouteMap
This getter creates a mapping between `courseRoutes` and `courseIds` by iterating over the `state.courseRoutes` array. It assigns each route value to the corresponding id key in the map object, excluding cases where the key already exists. Finally, it returns the resulting map object.

### courseContentRouteIdMap
This getter  returns a mapping between `route` paths and course IDs based on the `state.courseRoutes` array. It checks if the `id` matches `getters.courseStart` and adds the `route` to the map only if it is empty. For other cases, it assigns the `route` value to the corresponding ID key in the map.

### courseContentPathId
This getter takes the state object and a path parameter. It searches for a matching `route` in the `state.courseRoute`s array and returns the corresponding ID. If no match is found, it returns null.

## Mutations

### courseStructureDestructure
It copies the start and chapter information from a new backend course, destructures the course chapters into the `courseContent` property, and assigns the course chapters to the `courseChapters` property in the state.

### courseContentAdd 
adds a new content block to the `courseContent` property in the state, using the `content.id` as the key.

### courseContentSet 
Updates the content block by replacing the block with the matching ID with the passed in block. Also updates chapter slugs based on block changes.
Replaces the block in `state.courseContent` with block, and calls `chapterSlugUpdate` to update `state.courseChapters` based on block id, title, and name changes.

### courseContentSetProperty
This mutation updates the specified property of the content block matching the passed id in the `state.courseContent` object to the new value. If the property is `title`, it will also call `chapterSlugUpdate` to update the chapter slugs in `state.courseChapters`.

### courseContentRemove
Removes the content block from the `state.courseContent` object matching the passed `id`then uses the `stripKey` utility to filter out the specified block

### courseChaptersSet
This mutation sets the `courseChapters` in the Vuex state to the provided chapters array, after clearing any duplicate slugs.

### courseChapterAdd
This mutation adds the provided chapter to the `state.courseChapters` array in the Vuex state.

### courseChapterUpdateFollow
The mutation recursively updates the follow property of any item matching the passed id within the chapter tree to the new value. It defines a `updateOrDeeper` helper which either updates the property directly if the id matches, or recurses deeper to keep searching through children items in the tree.

### courseRoutesUpdate
Calls the `coursePathsGet` utility which generates routes based on the `state.courseChapters` then uses Vue.set to update the `state.courseRoutes` property with the returned routes

### setCourseContentAndNav
This mutation handles migrating the structure of a legacy course object without the new fields, to populate the equivalent properties in the Vuex state for the updated course format.

## Actions

### courseContentFetch
This action fetches a single content block from the backend API, then commits `courseContentSet` mutation to update the state with the received data. It handles both success and error scenarios through Promise chaining.

### courseContentPersist  
This action handles persisting content block data to the backend API. It checks parameters: `commit`- commit function, `verb`- the http request verb to use and `block`-block to update, shows loading state, makes the request and resolves/rejects the Promise depending on response.