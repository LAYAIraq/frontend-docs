Login
===============

This component organizes a login form for users. 

## Structure


### Dependencies

### Components

### Mixins
- locale 

Component Functionality
---------

### Computed Properties
- `errEmail`: checks the validity of an email input and returns (true) an error message if the input is invalid 
- `errForm`:checks the validity of multiple form inputs and returns (true) an error message if any of the inputs (password or email) are invalid
- `errPwd` : checks the validity of a password input and returns (true) an error message if the input is invalid

### Methods
- `resetPassword`: fire password reset request
- `showToast`: show a toast in root instance depending on type, is used for bootstrap variant and message
- `submit`: submit login, on success load profile, set login state, store token in local storage, reroute

#### Created
- relocate logged users