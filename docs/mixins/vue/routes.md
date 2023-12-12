Routes
===============
This mixin is to inject properties for route dependent props 

## Structure

### Dependencies
* `vuex`

Component Functionality
---------
### Props
- `coursePath`
  - `type`: prob
  - `default`: return empty string 
- `name`
  - `type`: prob
  - `default`: return empty string
- `chapters`
  - `type`: prob
  - `default`: return empty string
- `slug`
  - `type`: prob
  - `default`: return empty string
- `step`
  - `type`: prob
  - `default`: return empty string

### Computed Properties
#### VueX Getters
- `courseContent`
- `courseContentPathId`

#### Local
- `contentToDisplay`: return current content block
- `pathId`: return course content path 
