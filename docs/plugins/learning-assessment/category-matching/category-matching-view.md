Category Matching View
===============
This component is to view category matching assessment questions. Allows to view and answer category matching questions in an assessment.

## Structure

### Dependencies
* `@/assets/styles/flaggables.css`
* `AudioButton`from`@/components/helpers/audio-button.vue`
* `FlagIcon`from`@/compnents/course/flag/flag-icon.vue`

### Components
- `AudioButton`
- `CategoryMatchingView`
- `FlagIcon`

### Mixins
* `locale`
* `pluginView`

Component Functionality
---------

### Data
- `...this.viewDate`:Spread syntax to include viewData property passed from parent
- `checked`:Define checked property initially set to false
- `eval`:Define empty array to store evaluation results
- `showSolutionsBool`:Define property to control visibility of solutions, initially false
- `solution`:Define empty array to store user's solutions as index

### Computed Properties
#### VueX Getters
- `content`
- `courseSimple`

#### Local
- `taskAudioExists`: returns true if taskAudio object doesn't contain empty strings 

### Lifecycle Events
#### created
- call`mapSolutions`: Sets up mapping of pre-existing solution data to component's local storage arrays on component creation.

### Methods
- `check`: check if given answers are correct 
- `done`: execute function from onFinish[0] 
- `mapSolution`: initialize rendered ranges to the middle 