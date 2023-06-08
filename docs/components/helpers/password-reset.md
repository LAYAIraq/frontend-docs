PasswordReset
===============

This component handles the functionality of resetting a user's password.

## Structure

### Components
- `PasswordInput`: not lazily loaded b/c always visible

### Mixins
- locale
- password

Component Functionality
---------
### Data
- `busy`: boolean to block changes
- `resetSuccess`: boolean to indicate if password reset was successful

### Watchers
- `resetSuccess`: when the password reset is successful, the user is automatically redirected to the login page to log in with their new password.


### Methods
- `removeAuthenticated`: used to ensure that only one user is logged in at a time and to prevent unauthorized access to the application.
- `resetPassword`: fire set-pwd request that validates the taken and the new password.
- `showToast`: show a toast in root instance depending on type, is used for bootstrap variant and message

### Lifecycle events
#### Created
- call `removeAuthenticated`
