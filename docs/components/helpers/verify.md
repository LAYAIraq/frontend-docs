Verify
===============

This component verifies user email.

## Structure

### Dependencies
- `http`from `axios`

### Mixins
- locale

Component Functionality
---------

### Data
- `busy`: boolean to lock state when firing http request
- `success`: boolean to indicate http request resolved

### Methods
- `verifyUser`: tba

### Lifecycle events

#### Created
- call `verifyUser`
