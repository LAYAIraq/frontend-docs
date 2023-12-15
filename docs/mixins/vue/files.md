Files
===============
This component returns Strings and Icon for MIME Types

## Structure

### Dependencies
* `vuex`

Component Functionality
---------
### Computed Properties
#### VueX Getters
- `profileLanguage`

#### Local
- `types`: filter i18n file for mimeType keys 

### Methods
- `fileIcon`: return a fas class for expected MIME types
- `fileSize`: verbalize file size 
- `fileTypeString`: return textual description of file type 