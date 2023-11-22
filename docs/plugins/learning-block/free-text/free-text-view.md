FreeTextView
===============
This component is view free content block

## Structure

### Dependencies
* `@/assets/styles/flaggables.css`
* `Quill`from`quill`
* `quill/dist/quill.snow.css`

### Components
* [`FlagIcon`](../../course/flag/flag-icon)

### Mixins
* `locale`
* `pluginView`
Component Functionality
---------
### Data
- return `this.viewData`:  

### Lifecycle Events
#### mounted
- call `fetchContent`
   
### Methods
- `fetchConent`: fetch contents from quill