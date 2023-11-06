CourseNavPropertyEdit
===============
Editable property for course nav item .

## Structure

### Roots
- [`CourseNavChapter`](...)

### Mixins
* `locale`

Component Functionality
---------
### Props
- `callback`: type: Function, default: prop
- `display`: type: Function, default: prop
- `formPlaceholder`: type: String, default set to `Placeholder`
- `property`: type: String, required: true

### Data
- `edit`: set to false
- `newProperty`: initialized with `property.value`

### Computed Properties

#### Local
- `id`: retrieves the `id` property from the parent component.
- `propertyDisplay`: invokes the `display` method on the value of `this.property.value`.

### Watchers
- `property`: handler function is triggered when changes occur in the property data, `deep`set to true

### Lifecycle Events

### Methods
- `changeProperty`: switch edit, emit changed event with provided callback function
- `stateChange`: emit state-changed event with given value  
