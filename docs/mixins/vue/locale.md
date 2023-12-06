Locale
===============
This component is to expose i18n local to components 

## Structure

### Dependencies
* `i18n` from `../../assets/i18n`
* `kebabToCamel` from `@/mixins/general/helpers`
* `vuex`

Component Functionality
---------

### Computed Properties
#### VueX Getters
- `profileLanguage`
- `courseLanguage`

#### Local
- `courseLangIsAr`: checks if Arabic script language is set, for rtl shenanigans 
- `i18n`: return local for user language property
- `langIsAr`: checks if Arabic script language is set, for rtl shenanigans

### Methods
- `linkReplacement`: return a string pattern for strings, intended to use with replacePattern 
- `replacePattern`: (str, pattern, replacement): alias for str.replace( pattern, replacement) 
- `typeName`: returns name of content block in locale 
- `y18`: returns i18n[prop] if it exists, the English equivalent if it doesn't, also falls back if key doesn't exist altogether 
