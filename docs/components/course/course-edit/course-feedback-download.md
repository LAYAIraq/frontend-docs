CourseFeedbackDownload 
===============
This component is used to download received feedback 

## Structure

### Roots
* `CourseEditTools`

### Dependencies
* `jsPDF`from `jspdf`

### Mixins
* `locale`
* `storeHandler`

Component Functionality
---------
### Data
- `feedback`: is set to null to indicates that there is no feedback data available yet.

### Computed Properties
### Computed Actions
- `enrollmentsCourseFetch`

#### VueX Getters
- `course`
- `courseId`
- `enrollmentFeedback`

### Lifecycle Events

#### created
- `this.feedback = this.getFeedback`: sets the value of the feedback property to the result of calling the getFeedback method.
### Methods
- `getFeedback`: gets feedback from store 
- `printPDF`: prints feedback in a PDF to download 
- `printBlock`: prints a headline for a block of feedback
- `printChoices`: prints choices answer into PDF
- `printFreetext`: prints freetext answers into PDF 
- `printRating`: prints rating answers into PDF 
