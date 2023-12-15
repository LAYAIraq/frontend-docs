Authentication  
===============

This store module is to organize authentications for users, including login, logout, and account verification actions, using the Axios library for HTTP requests. It manages state variables for userId and online status and provides getters to access them.

## Dependencies
- `http` from `axios`

## State
- `userId`: initialized to `0`
- `onLine`: set to false 

## Getters

### userId: 
The provided getter, retrieves and returns the `number` `userId` from the `state`.

### userOnline
The getter returns true if the user is logged in based on the `online` state variable.


## Mutations

### login
updates the state to set the user as online, assigns the provided `userId` to the `state`, and sets the `Authorization` token for future `HTTP` requests using `axios`.

### logout 
sets `online` `state` variable to false, indicating that the user is no longer logged in.
sets the `userId` `state` variable to -1, indicating that there is no active user.
removes the `Authorization` token from the `http` object in order to revoke the user's authenticated status and prevent further authorized requests. 

## Actions

### accountVerify
The function fires a request to verify a user's account by making a GET request to the `/accounts/confirm` endpoint with the provided `uid` and verificationToken. 
- `data`
  - `uid`: number 
  - `token`: string
It returns a promise that resolves with null if the request is successful, or rejects with an error otherwise.

### sendCredentials  
Initiates a login request by making a POST request to the `accounts/login` endpoint with the provided `email` and `password`. 
- `state`
- `commit`
- `dispatch`
- `data`
  - `email`: string
  - `password`: string 
It returns a promise that resolves with the login data if the request is successful. 
It also triggers other actions to fetch the user's profile and role, and returns additional data for local storage.
