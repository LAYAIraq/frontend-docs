ScrollToTop
===============

This component shows little arrow to return to the top of a page without having to manually scroll up and is named ScrollToTop.

## Structure

### Mixins
- locale

Component Functionality
---------
### Data
- `show` boolean to indicate if button is shown
### Methods
- `scrollThreshold`: sets `show` to true if scrolled more than 200px.
- `scrollTop`: scrolls to top of the window

#### Created
- Add listener to execute `scrollThreshold` on every scroll event

#### Destroyed
- Remove listener for scroll events.
