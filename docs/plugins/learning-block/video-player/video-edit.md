VideoEdit 
===============
This component is edit Plyr content block

## Structure

### Dependencies
* `deepCopy` from `@/mixins/general/helpers`

### Components
* [`ContentTitleEidt`](../../helpers/content-title-edit)

### Mixins
* `locale`
* `pluginEdit`
* `routes`
* `tooltipIcon`

Component Functionality
---------
### Data
- `src`: set empty string 
- `host`: an empty string 
- `title`: an object contains:
  - `text`: an empty string
  - `flagged`: boolean initialized to false
  - `show`: boolean initialized to false
  - `id`: an empty string 
- `videoFlag` an object contains:
  - `flagged`: boolean initialized to false
  - `id`: an empty string
- `captions`: an object contains:
  - `default`: set to null
  - `tracks`: an empty array

### Computed Properties
#### VueX Getters
- `courseContent`

#### Local
- `captionTypes`: return the W3C caption types excluding metadata 
- `correctURL`: checks if video is on yt or vimeo 
- `urlMsg`: return warning if URL is not supported 
- `validUrl`: check if string is a valid URL according to RFC 3886 
- `validVimeoUrl`: check if URL contains vimeo or consists of Numbers 
- `validYtUrl`: check if URL contains youtu or consists of Numbers 

### Lifecycle Events
#### created
- checks `this.edit` is in edit mode.
- calls `this.fetchData` method if in edit mode.

### Methods
- `addCaption`: add caption object to caption tracks array 
- `fetchData`: fetch data from vuex and make data property 
- `makeDefault`: make element at index i the default track 
- `removeCaption`: remove caption at given index 
- `setHost`: set host variable to val