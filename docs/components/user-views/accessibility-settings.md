AccessibilitySettings 
===============

Accessibility Settings, such as content preferences and text size 

## Structure

### Dependencies
- `fontOptions` from `@/options/font-options` ?//inaktiv//
- `fontSizeOptions` from `@/options/font-size-options`

### Components

### Mixins
- `locale`

### VueX Store Modules

Component Functionality
---------

### Computed Properties

#### VueX Getters
- `profile`
- `userId`
- `preferencesFont`,
- `PreferencesMedia`

#### VueX Mutations
- `preferencesSet`: set all media preferences at once ?? 

#### Local
- `fontOptionsIntro`: add placeholder in `locale`to `fontOptions`
- `fontSizeOptions`: add font size options  
- `sizeChosen`: returns index of chosen size in `fontSizeOptions`, sets pref. size when chnaged 
