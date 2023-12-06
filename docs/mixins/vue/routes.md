Routes
===============
This component is to inject properties for route dependent props 

## Structure

### Dependencies
* `vuex`

Component Functionality
---------
### Props
- `coursePath`
  - `type`: `String`
  - `default`: return empty string 
- `name`
  - `type`: `String`
  - `default`: return empty string
- `chapters`
  - `type`: `String`
  - `default`: return empty string
- `slug`
  - `type`: `String`
  - `default`: return empty string
- `step`
  - `type`: `String`
  - `default`: return empty string

### Computed Properties
#### VueX Getters
- `courseContent`
- `courseContentPathId`

#### Local
- `contentToDIsplay`: return current content block
- `pathId`: return course content path 
