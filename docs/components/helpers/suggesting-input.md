SuggestingInput
===============
This component is used to implement a suggesting input box.

## Structure

### Roots
- [`CourseNavFollowEdit`](..`@/components/course/course-nav/course-nav-follow-edit.vue`)

### Dependencies
* `camelToRender`,`filterObject`,`kebabToCamel`from `@/mixins/general/helpers`

### Mixins
* `locale`

Component Functionality
---------
### Props
- `domain`: the input data on which to search for keys. type: Array, Object, required: true
- `dropDownButtonText`: text for dropdown menu button. type: String, default: `Select tags`
- `inLine`: whether component is used inLine or modal. type: Boolean, default: true
- `keys`: the keys on which to narrow the search domain down. type: String, Array, default: null
- `nestedKey`: key to use if search domain has nested objects. type: String, default: null
- `noResultsText`: text to be displayed if search yields no results. type: String, default: `No results found`
- `previousSelection`: already selected input. type: String, Array, default: null
- `searchInputPlaceholder`: placeholder for search input. type: String, default: `Type for searching`
- `searchLabelText`: label for search input field. type: String, default: `Search for tags`
- `submitButtonText`: text for submitting a button. type: String, default: `Submit`
- `submitButton`: whether or not to render a button for submitting. type: Boolean, default: true
- `tagsNeeded`: number of tags to select. type: Number, default: 1
- `titileLabelText`: title above Form. type: String, default: ``

### Data
- `searchTerm`: initialized with an empty String 
- `selectedTags`: initialized with an empty Array 

### Computed Properties

#### Local
- `notFound`: return noResultText when searchResult has length 0 
- `resultObject`: 
- `searchDomain`: converts input domain: if it's an object, transform into array of filtered objects, if it's array of objects, filter, if array of primitive values, return domain
- `searchQuery`: sanitize search input, return String trimmed and lowercase search term 
- `searchResult`: filter searchDomain for input, checking each value if search domain consists of objects, return {*[]} array of values satisfying search query
- `selectedTagsNo`: returns the length of the selectedTags array. It provides the count of selected tags in the array.

### Watchers
- `selectedTagsNo(v)`:emit tags-selected event when component selected tags matches the number of tags needed. Only applicable when submitButton prop is false

### Lifecycle Events
#### created
- sets the initial value of `selectedTags` based on the value of `previousSelection`, either as an array or a single value. If `previousSelection` is not provided or is falsy, `selectedTags` is set as an empty array.

### Methods
- `kebabToCamel`: 
- `objectRender`: enumerating them as Uppercase `Key: Value`, return {string} stringified `Test: Value`
- `optionSelect`: add selected option to tags array in BFormTags, reset searchTerm
- `searchResultRender`: render search result depending on type
- `tagRender`: represent selected object by filtering keys, return {*|object} representation of element in tag
- `tagsSelected`: emit tags-selected event with single item or array