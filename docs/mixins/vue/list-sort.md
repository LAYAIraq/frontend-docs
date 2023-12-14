ListSort
===============
This mixin is to define methods for sorting lists

## Structure

### Dependencies
* `as locale` from `../../assets/i18n`

Component Functionality
---------
### Data
- `sortAsc`: boolean set to true
- `sortBy`: empty string 

### Computed Properties
#### VueX Getters
- `profileLanguage`

#### Local
- `tooltips`: filters i18n file for needed tooltip keys 

### Methods
- `sortByProp`: sort list by given property 
- `sortIcon`: return icon css class depending on how names are sorted 
- `sortList`: sort list
- `sortTooltip`: returns the appropriate tooltip text based on the icon class applied to the given prop after checking the prop's class to determine if it is sorted ascending, descending or not sorted.
- `toggleSortDir`: toggle sort direction 