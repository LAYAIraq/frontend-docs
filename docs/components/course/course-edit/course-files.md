CourseFiles
===============
This component is used as a list of files uploaded to the course 

## Structure

### Roots
* `CourseContent`

### Dependencies
* `api`from `@/backend-url`

### Components
- `UploadFile`

### Mixins
* `files`
* `listSort`
* `locale`
* `tooltipIcon`

Component Functionality
---------

### Data
- `addUpload`: boolean, indicates whether to show or hide the file upload UI.
- `files`: array, stores the selected files to be uploaded.
- `fileToDelete`: set to null, stores the file to be deleted.
- `uploaded`: boolean, indicates whether the files have been uploaded successfully or not.
- `uploadedFiles`: array, stores the filenames of the uploaded files.

### Computed Properties
#### VueX Getters
- `courseFiles`
- `courseStorage`

#### Local
- `sortedFiles`: calls the sortList method and passes in the courseFiles property as an argument.
- `step`: return step of current content block. 

### Lifecycle Events
#### beforeDestroy
- `$store.dispatch`(`courseFilesStore`): ensures that any changes made to the course files during its lifecycle are persisted in the database and can be retrieved later if needed.

### Methods
- `fileDelete`: propagate file to delete to vuex, nullify the global variable 
- `fileDeleteConfirm`: mark file as to delete, show prompt 
- `urlCopy`: copy URL for that file 
- `urlGet`: get store download URL for file 

