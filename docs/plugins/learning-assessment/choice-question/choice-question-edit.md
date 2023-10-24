Choice Question Edit 
===============
This component to manage choice question blocks for assessments. Edit details like the question text, available answer choices, and correct response when using this component. It provides an interface for updating the content of multiple choice questions.

## Structure

### Dependencies
* `deepCopy`from `@/mixins/general/helpers`
* `v4 as uuid4`from`uuid`

### Components
- `ChoiceQuestionEdit`

### Mixins
* `array`
* `locale`
* `pluginEdit`
* `routes`
* `tooltipIcon`

Component Functionality
---------

### Data
- `maxTries`: Attempts allowed 
- `multiple`
- `options`: Answer choices array
- `single`: Question type identifier 
- `solution`:Correct index number
- `solutions`: Correct choice(s) flagged
- `taskAudio`: Audio
- `task`: Question text
- `tf`: True /false identifier 
- `title`: Question title
- `variation`: Variation identifier 

### Computed Properties
#### VueX Getters
- `courseContent`
- `courseSimple`

### Watchers
- `multiple (val)`: reset solutions when changed to single choice 
- `solution (val)`: reset solutions array to accept solution at index val, param `val`integer value for solution. 

### Lifecycle Events
#### created
- call`fetchData`if editing existing question to populate fields Otherwise, populates default title and adds first choice option.

### Methods
- `fetchData`: fetch data from vuex and make data property 
- `newItem`: create new Item, returns choice object to add to options list
- `populateTrueFalse`: add the correct answer options if true and false is selected 
- `switchToIF`: prevent change to true/false before modal `ok` is clicked. 