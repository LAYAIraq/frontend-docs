Applications 
===============

This store module is to organize editor application votes.  It is designed to handle the voting process within the application, ensuring that votes are properly recorded, stored, and organized.

## Dependencies
- `http` from `axios`
- `Vue` from `vue`

## State
- `applicationList`: an empty array
- `editorNumber`: initialized to `0`
- `editorVotes`: an empty array

## Getters

### applicationList: 
The provided getter, retrieves the applicationList array from the state object.
- `applicationText`: string
- `areaOfExpertise`: string
- `fullName`: string
- `id`: number
- `institution`: string
- `votes?`: number 

### editorVotes 
This getter returns the `editorVotes` array from the state object, which contains objects with properties `applicationId` (number), `editorId` (number), and `vote` (boolean).
- `applicationId`: number
- `editorId`: number
- `vote`: boolean 
### editorNumber
This getter returns the value of `editorNumber` from the state object, which is a number.

### userApplication
This getter retrieves the first element of the `applicationList` array from the state object, which contains properties such as `id` (number), `applicationText` (string), `areaOfExpertise` (string), `fullName` (string), and `institution` (string).
- `id`: number
- `applicationText`: string
- `areaOfExpertise`: string
- `fullName`: string
- `institute`: string

## Mutations

### applicationAdd
This function takes the state object with an `applicationList` array and an `application` object as parameters. It adds the `application` object to the end of the `applicationList` array in the state object.

### applicationCreate 
It takes the state object with an empty `applicationList` array and an `application` object as parameters. It uses the Vue.set method to set the first element of the `applicationList` array in the state object to the provided `application` object.

### applicationDecide 
It modifies the state by updating the `status` and `decidedOn` properties of an application in the `applicationList` array. It does so by searching for the application with a matching `applicationId` in the state. Once found, it assigns the provided `decision` value to the `status` property, indicating the decision made for the application. Additionally, it sets the `decidedOn` property to the current timestamp obtained from Date.now(), representing the time when the decision was made.

### applicationEdit
It allows editing an application in the `applicationList` array in the state. It first checks if the `applicationList` is empty and logs an error if it is. Then it verifies if the ID of the first application in the list matches the provided ID. If they don't match, it logs an error. If the IDs match, it updates the application's properties by merging the existing application object with the provided data object using Vue.set to retain reactivity.

### applicationListClear
It clears the `applicationList` array in the state by assigning an empty array to it, effectively removing all the application objects from the list.

### editorNumberSet 
It sets the value of `editorNumber` in the state to the provided `num` value, effectively updating the editor number with a new value. 

### editorVoteAdd
It adds a new vote to the `editorVotes` array in the state. It updates the associated application's vote count in the `applicationList` array based on the provided vote, and uses Vue.set to retain reactivity.

### editorVoteChange 
This function  allows an editor to change their vote for a specific application. It retrieves the existing vote for the editor and application, updates the necessary properties, and updates the vote count for the application in the `applicationList` array.

### updatePersistedVote 
This function updates a persisted vote in the `editorVotes` array in the state. It finds the index of the editor's vote for the specific application in the array based on the provided `editorId` and `applicationId`. Then, it uses Vue.set to update the vote at that index with the provided data object. 

## Actions

### applicationsFetch
This function is to get 10 undecided applications, when n already in state 
- `state`
- `commit`
- `dispatch`
This function returns new `Promise` with `resolve`, `reject`

### editorNumberFetch 
is to retrieve number of editors from db 
- `commit`

### editorVoteCreate 
This function is to persist vote in database, update editorVote entry with persisted data 
- `state`: state variables 
- `commit`: state mutation 
- `applicationId`: id of vote application 
- `editorId`: id of voting editor 
- `vote`: value of vote 
This function returns new `Promise` with `resolve`, `reject`

### editorVotesFetch 
This function is to retrieve existing votes for specified application 
- `commit`
This function returns new `Promise` with `resolve`, `reject`

### editorVoteUpdate 
This function is to send post request for vote 
- `state`
This function returns new `Promise` with `resolve`, `reject`

### userApplicationCreate
This function is to send post request for application 
- `getters`: consists userApplication
This function returns new `Promise` with `resolve`, `reject`

### userApplicationDecide 
This function is to send patch request for decided application 
- `getters`: consists userApplication
This function returns new `Promise` with `resolve`, `reject`

### userApplicationFetch 
This function is to return user's application if it exists 
- `state`
- `commit`
- `userId`
This function returns new `Promise` with `resolve`, `reject`

### userApplicationUpdate 
This function is to send patch request for application 
- `state`
This function returns new `Promise` with `resolve`, `reject`