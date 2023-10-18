FlagQuestion
===============
This component is to display flag question view 

## Structure

### Roots
* `Flag`

### Dependencies
* `@/assets/styles/flag-styles.css`

### Mixins
* `locale`
* `tooltipIcon`

Component Functionality
---------

### Props
- `id`:`type`: `String`, if no value it will `default`return empty `String`

### Data
- `answerSent`: set to false
- `anonymous`: set to false
- `newAnswer`: empty string
- `question`: empty string
- `unflagged`: set to false

### Computed Properties
#### VueX Getters

- `courseFlags`
- `courseCreator`
- `courseId`
- `userId`

### Methods
- `setFlagQuestion`: bundle flag info and store it