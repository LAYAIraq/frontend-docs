EditorPanel
===============

Editor panel view 

## Structure

### Dependencies

### Components

### Mixins
- `locale`

### VueX Store Modules

Component Functionality
---------

### Computed Properties
#### VueX Actions
- `applicationsFetch`
- `editorVoteUpdateAll`

#### VueX Getters
- `applicationList`
- `editorVotes`
- `isEditor`
- `userId`

#### VueX Mutations
- `editorVoteAdd`
- `editorVoteChange`

#### Local
- `acceptThreshold`: returns number of necessary votes to be accepted currently fixed value, can be computed if wanted 
- `approved`: returns {boolean} if user has approved the current application 
- `currentApplication`: returns copy of application for decision modal 
- `existingVote`: returns user's decision on current application 

### Methods
- `prepareViewModal`: deep copy values from store for render 
- `revokeVote`: change vote from yes or no 
- `showDecision`: show decision of user for current application  
- `voteOnApplication`: vote on application 

### Lifecycle Events

#### created
- `$router.replace`: reroute non-editors 
- call `applicationsFetch`: get applications

#### beforeDestroy
- call `editorVoteUpdateAll`: persist votes in backend 