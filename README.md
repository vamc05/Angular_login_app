#  Angular login_app

## Angular Version 1.x

We are providing Login app. Developed this app  have used HTML, CSS and AngularJS.


## About Login App

The authentication service contains methods for authenticating a user, setting credentials and clearing credentials 
from the HTTP "Authorization" headers used by the AngularJS $http service, so effectively logging in and out.

The example uses dummy authentication in order to show the example working on plunker without a back end, but real 
authentication can be setup by following the comments in the Login function.

## AngularJS Fake User Service (Local Storage)

A fake user service that stores users in local storage in the browser, it mimics the behaviour of the real user service by returning promises and using $timeout.

When creating a user, the service checks if a username is already taken and returns an error message, in a real implementation using a web service this action would be performed on the server.

To switch between using this fake user service and the real one above update the scripts section at the bottom of the index.html file.

## AngularJS Login Controller

The Login Controller clears the user credentials on load which logs the user out if they were logged in.

The login function exposed by the controller calls the Authentication Service to authenticate the username and password entered into the view.

## AngularJS Login View


The Login View contains a small form with the usual fields for username and password, and some validation directives and messages.


## AngularJS Register Controller


The Register Controller exposes a single register method which is called from the register view when the form is submitted. The register method then calls the UserService.Create method to save the new user.

## AngularJS App.js


The part of this file related to authentication is in the run function, when the app starts it checks if there's a cookie containing user credentials meaning the user has already logged in, this is to keep the user logged in after a page refresh.

On each location change there's a check to verify that the user is logged in if trying to access a restricted page, if not they're redirected to the login page.
