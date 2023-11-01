UploadAvatar
===============
This component to upload and crop avatar.
## Structure

### Dependencies
* `api`from`@/backend-url`
* `Cropper`from`cropperjs`

### Components
- [`FileUpload`](..upload-file)

### Mixins
* `locale` 

Component Functionality
---------
### Props
- `oldAvatar`:type:`String`, default value empty string

### Data
- `cropper`: initialized with a value of `false`
- `edit`: initialized with a value of `false`
- `files`: initialized with an empty `Array`

### Computed Properties

### Local
- `downloadURL`: return the download URL for images and provides additional details.  
- `header`: return authorization headers for upload.
- `postAvatar`: return the URL for posting avatars and provides additional details.

### Watchers
- `edit`: If the new value is truthy:
    - Create a new `Cropper` instance with specific configuration options.
    - If the new value is falsy:
    - Destroy the existing `Cropper` instance if it exists.

### Methods
- `alert(msg)`: displays an alert with the given message.
- `editSave`: saves the edited image by retrieving canvas and image data, adjusting scaling if necessary, creating a cropped blob, and updating the file in the upload component.
- `inputFilter`: filters non-image files and sets the file URL for new files.
- `setFileURL`: sets the URL for the uploaded file based on the response from the server.