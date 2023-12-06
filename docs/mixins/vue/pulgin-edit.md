PluginEdit
===============
This component uses mixin to populate plugin data on create, and inject properties for plugin edit component

## Structure

### Dependencies
* `v4 as uuidv4` from `uuid`

Component Functionality
---------
### Props
- `edit`
  - `type`: `Boolean`
  - `required`: boolean set to true

### Methods
- `taskTitlePopulate`: initializes the title and task objects with default empty string text, a generated uuid id, and a false flagged property.
