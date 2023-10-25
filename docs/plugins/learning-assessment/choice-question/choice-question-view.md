Choice Question View
===============
This component to view a Choice Question block and select from option choices when viewing an assessment.
## Structure

### Dependencies
* `@/assets/styles/flaggables.css`
* `AudioButton`from`@/components/helpers/audio-button.vue`
* `FlagIcon`from`@/compnents/course/flag/flag-icon.vue`

### Components
- `AudioButton`
- `ChoiceQuestionView`
- `FlagIcon`

### Mixins
* `locale`
* `pluginView`

Component Functionality
---------
### Data
- `answers`: Array for user answers
- `checked`: Array to track checked options
- `eval`: Evaluation results
- `feedback`: Feedback text
- `freeze`: Boolean set to `false` to lock options 
- `showSolutions`: Array to show the correct answers 
- `showSolutionsBool`: Boolean set to `false`toggle solution visibility  
- `tries`: Number of attempts   

### Computed Properties
#### VueX Getters
- `courseSimple`

### Local
- `feedbackId`: create an identifier string 
- `textAudioExists`: returns true if taskAudio object doesn't contain empty strings  

### Lifecycle Events
#### created
- call`populateShowSolutions` to ensure it's ready to display properly on load.

### Methods
- `check`: check user's answers, give feedback accordingly 
- `correct`: returns true if user choice is correct 
- `diffSolution`: check if given answers are correct, mark with check if yes, cross if not 
- `incorrect`: returns true if answer is incorrect 
- `markAnswers`: marks questions that have been checked 
- `populateShowSolutions`: fills the showSolutions array to be used when the used clicks the 'show solutions' button  