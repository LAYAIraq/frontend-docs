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
- `applicationId`: number
- `editorId`: number
- `vote`: boolean 
### editorNumber
### userApplication
- `id`: number
- `applicationText`: string
- `areaOfExpertise`: string
- `fullName`: string
- `institute`: string

## Mutations

### applicationAdd
append application to applicationList 

### applicationCreate 
create new application is applicationsList 

### applicationDecide 
use to decide an application 

### applicationEdit
only call applicants, updated instance returned by userApplication getter 

### applicationListClear
This function is to reset application list 

### editorNumberSet 
This function is to set number of editors 

### editorVoteAdd
This function is to push editorVote into editorVotes array, update application's vote count accordingly 

### editorVoteChange 
This function is to change value for editor's vote on application, call only if vote for editor already exists

### updatePersistedVote 
This function is to change state after new vote is saved in db 

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
- 
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