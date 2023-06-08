Register
===============

This component is responsible for displaying a user registration form and handling the submission of user data to a server for account creation.

## Structure


### Components
- `PasswordInput`

### Mixins
- locale
- password

### Computed Properties
- `errEmail`: form validation for email
- `errForm`: form validation altogether
- `errName`: form validation for name
- `noInput`: return true if no input is set

### Methods
- `isNameTaken`: fire request to check if name is already taken
- `isEmailTaken`: fire request to check if email is already taken
- `submit`:  collect requests for changes, then shoot them

### Watchers
- `name`:check for wrong characters in name, pushing them to wrongNameCharacters for display
- `email`: check if @ and . are present in email

#### Created
- relocate users that are logged on because logged users don't need to register anymore
