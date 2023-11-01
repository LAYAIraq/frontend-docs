UploadFile
===============

This component allows users to upload files, select from disk or drag & drop.

## Structure

### Roots
* [`UploadAvatar`](../upload-avatar)

### Mixins
- files
- locale

### Components
- `vue-upload-component`: Lazily loaded

Component Functionality
---------
### Data
- `addUpload`: boolean to show the upload interface
- `files`: list of files to upload
- `uploaded`: boolean to indicate upload success
- `uploadedFiles`: list of uploaded files (used b/c names are changed during upload)

### Computed Properties
- `headers`: returns an object containing an Authorization header. The header value is obtained from the 'id' property of an object stored in the web browser's local storage.
- `upLoadUrl`: return course storage URL for upload

#### VueX Getters
- `courseFiles`
- `courseStorage`

### Watchers
- `files`: watcher files: watch for changes in files data prop, change uploaded property if an action happened in upload.
- `uploaded`: watcher uploaded: watch for changes in uploaded prop, call `fileListUpdate()`
- `uploadedFiles`: watch for changes in uploadedFiles, fire `courseFilesUpdate()` when there are any.

### Methods
- `checkDuplicate`: check if a file with same name and size already exists in a course.
- `checkSizeExcess`: check if a file is too large.
- `courseFilesUpdate`: store new files in vuex store by calling `courseFilesUpdate` mutation.
- `fileListUpdate`: update list of files that have been added in this component.
- `fileUpload`: proceed a duplicate check, then upload the file to uploadUrl(). ?fileUpload or uploadFile?
- `_removeFile`: remove file from list at index idx


