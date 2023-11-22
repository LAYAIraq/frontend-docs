FeedbackView
===============
This component is to display Course Feedback content block

## Structure

### Dependencies
* `@/assets/styles/flaggables.css`

### Components
* [`AudioButton`](../../helpers/audio-button)
* [`FlagIcon`](../../course/flag/flag-icon)
* [`StarRating`](..vue-rate-it)

### Mixins
* `locale`
* `pluginView`
* `watchContent`

Component Functionality
---------
### Data
- return`this.viewData`
- `answered`: an empty array 
- `choice`: an empty array: user solution as index 
- `freetext`: an empty string 
- `prevFeedback`: an empty string 
- `rating`: set to `0`

### Computed Properties
#### VueX Getters
- `content`
- `courseId`
- `courseSimple`
- `enrollmentFeedback`
- `userEnrolled`

#### Local
- `taskAudioExists`: return true if taskAudio object doesn't contain empty strings

### Lifecycle Events
#### created
- checks `!this.viewData` property is falsy
- call `this.fetchData` method
- call `mapSolutions` method
- call `getPervFeedback` method
- check `!this.userEnrolled` is falsy
- Dispatch `this.$store.dispatch('enrollmentFetch', this.courseId)`

#### beforeDestroy
- `this.storeFeedback`: add saving feedback data 

### Methods
- `bundleFeedback`: bundle input in Object to persist 
- `done`: execute function from onFinish[0] 
- `getPrevFeedback`: fetch eventual previous feedback 
- `mapSolutions`: initialize rendered ranges to the middle
- `storeFeedback`: emit feedback to parent component, show toast 
