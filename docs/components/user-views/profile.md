Profile
===============
This  component provides a user profile settings page. It allows users to view and edit important account information such as their password and avatar. Through this component, a user can manage settings related to their profile in one centralized location. They can update their password for added security or change their avatar image to customize their public profile display.

## Structure

### Dependencies
* `AccessibilitiySettings`from`@/components/user-views/accessibility-settings`
* `AuthorApplication`from`@/components/user-views/author-application`
* `PasswordInput`from`@/components/helpers/password-input.vue`
* `UploadAvatar`from`@/components/helpers/upload-avatar`
* `api`from`@/backend-url`
* `deepCopy`from`@/mixins/general/helpers`
* `institutions`from`@/options/instituion.ts`
* `occupations`from`@/options/occupation.ts`

### Components
- `AccessibilitySettings`
- `AuthorApplication`
- `UploadAvatar`
- `PasswordInput`: not lazily loaded b/c always visible

### Mixins
* `locale`
* `password`

Component Functionality
---------
### Data
- `avatar`: set to `null`
- `busy`: boolean state set to`false`
- `emailNewConfirm`: set to `null`
- `emailNewTaken`: set to `null`
- `emailNew`: empty placeholder
- `emailOld`: empty placeholder
- `emailRepeat'`: empty placeholder
- `passwordMessage`: empty placeholder
- `passwordOld`: empty placeholder
- `prefs`: empty object 
- `usernameNew`: empty placeholder
- `usernameTaken`: set to `null`


### Computed Properties
#### VueX Getters

- `fullName`
- `instituion`
- `occupation`
- `passwordRepeat`
- `password`
- `profile`
- `userId`

#### Local
- `avatarURL`: return URL of user avatar 
- `institutionChoose`: to add institutions 
- `occupationChoose`: add occupation 
- `passwordInputNew`: returns something when password input is set 
- `passwordInputOk`: returns true if no new password set or new password is secure 

### Watchers
- `emailNew`: reset email taken if email input changes 
- `usernameNew`: reset username taken if username input changes 

### Lifecycle Events

#### created
- call`setProfileForRender`

#### beforeDestroy
- call `profileUpdate`

### Methods
- `avatarChange`: change avatar if requirements are fulfilled 
- `emailChange`: change email if requirements are fulfilled
- `passwordChange`: change password if requirements are fulfilled
- `setProfileForRender`: deep copy prefs for mutation, render 
- `submit`: get password change request and fire it 
- `usernameChange`: check if username is taken

#### mapActions
- `checkEmailTaken`
- `checkNameTaken`
- `passwordUpdate`
- `profileUpdate`

#### mapMutations
- `emailSet`
- `fullNameSet`
- `institutionSet`
- `occupationSet`
- `preferencesSet`
- `usernameSet`
