PasswordInput
===============

This component allows users to enter a password in a text field and provides options for showing or hiding the entered characters.

## Structure

### Roots
- `Register`
- `PasswordReset`
- `Profile`


### Dependencies
- `Password` from 'vue-pasword-strength-meter'


### Mixins
- `locale`

Component Functionality
---------

### Props
- `inputPWD`: input password
- `inputPwdRepeat`:repeat input password
- `labelIconsOnly` : boolean for label output
- `labelWidth` : width of labeling, uses bootstrap col widths
- `newInput` : boolean if it's a new password
- `secureLength` : secure pwd length, shows indicator if input is less
- `showWordedStrength` : boolean for showing verbal output
- `showPasswordSuggestions` : boolean for showing suggestions to improve password

### Computed Properties
#### VueX Getters
- `password`
- `passwordRepeat`

#### Local
- `inputWidh`: returns number for matching label in bootstrap
- `pwDiffMsg`: returns a message if passwords differ
- `pwMatch`: returns true if passwords are identical
- `pwdRepeat`: get and set store property passwordRepeat, this is used b/c unusual behavior when using props
- `pwdSecureLength`: returns true if password exceeds minimum length
- `pwdSet`:get and set store property password, this is used b/c unusual behavior when using props
- `wordedPwdStrength`: return localized message for password strength (e.g. 'Password is not secure')

### Methods
- `pwdHints`: this component is used component to generate password hints and warnings for the user.
- `setPwdStrength`: this component is used to set the strength level of a password entered by the user.

### Watchers
- `pwdMatch`: this component emits a `compliantLength` event using the $emit method and passes the value of the 'pwdSecureLength' property as a payload.
