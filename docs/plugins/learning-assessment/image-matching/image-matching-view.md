ImageMatchingView  
===============
This component is to view an Image Matching assessment block 

## Structure

### Dependencies
* `stripKey`from`@/mixins/general/helpers`
* `@/assets/styles/flaggables.css`

### Components
* [`AudioButton`](../../helpers/audio-button)
* [`FlagIcon`](../../course/flag/flag-icon)

### Mixins
* `locale`
* `pluginView`

Component Functionality
---------
### Data
- return `this.viewData`
- `allAnswersChosen`: boolean set to false 
- `defaultOption`: an empty string
- `eval`: an empty array
- `freez`: boolean set to false
- `showSolutionsBool`: boolean set to false 
- `solution`: an empty array 

### Computed Properties
#### VueX Getters
- `courseSimple`

#### Local
- `options`: map pairs to their relation 

### Watchers
- `content`: refers to a property within the component that is being watched for changes
  - `deep`: set to true, 
  - call `handler`: will be executed when changes are detected in the content property
  - call `this.fetchData`: responsible for retrieving data from an external source

### Lifecycle Events
#### created
-  sets `defaultOption` using a translation or localization function. Then, it loops through each element in the `pairs`and pushes -1 to `solution` array, initializing it with default values.

### Methods
- `check`: check if User's solution is correct  
- `done`: execute first function from onFinish   
- `reset`: reset relations to default 
