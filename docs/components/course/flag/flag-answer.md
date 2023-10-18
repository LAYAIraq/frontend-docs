FlagAnswer
===============
This component is to display flag answer view. 
## Structure

### Roots
* `Flag`

### Dependencies
* `v4 as uuidv4`from 'uuid'

### Mixins
* `locale`
* `time`

Component Functionality
---------

### Data
- `answerIsQuestion`: set to false
- `answerSent`: set to false
- `answerToEdit`: empty string
- `editAnswerIsQuestion`: set to false
- `editAnswer`: empty string
- `editQuestion`: set to false
- `newAnswer`: empty string
- `newFlag`: set to null
- `noNewAnswer`: set to false
- `question`: empty string
- `sortedAnswers`: empty array
- `subFocus`: set to false

### Computed Properties
#### VueX Getters

- `content`
- `courseCreator`
- `courseFlags`
- `userId`

#### Local
- `anonQuestion`: returns if question was asked anonympusly
- `currentFlag`: returns current flag if any is set 
- `flagAuthor`: return ID of flag author 
- `isCourseCreator`: returns if user is course creator 

### Watchers
- `currentFlag`: set `deep`to `true`, set `handler`this.question to `this.currentFlag.question.text`

### Lifecycle Events

#### created
- set `this.question` to `this.currentFlag.question.text`, call `this.checkForNewstAnswer`, call `this.updateSortedAnswers`

### Methods
- `addAnswer`: send answer to store
- `answerHint`: returns string depending on answer state
- `checkForNewstAnswer`: switch noNewAnswer to true if current user has written the latest answer
- `prepareAnswerEdit`: set editAnswer to current answer
- `saveAnswer`: save edited answer in store, switch editAnswer bool
- `saveQuestion`: save edit to flag question, toggle editQuestion bool
- `showUserName`: show username
- `timeAndDate`: renders simple timestamp
- `updateFilteredFlag`: update filteredFlag
- `updateSortedAnswers`: renew sorted answers by score
- `vote`: upvote downvote an answer
- `voted`: returns user's vote on answer

