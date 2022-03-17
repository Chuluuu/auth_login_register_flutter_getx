# Authentication Login and Register with Flutter Getx
Flutter Getx project that covered a best architecture and functionality of Authentication, Login and Register using Rest API
In this project I used the powerful features of Getx like state management, Dependency injection, Route management, localStorage...

## Screenshots
| Login Screen  | Register screen | Offline pop-up  |
| :------------ | :------------- | :------------ |
| <img src="https://raw.githubusercontent.com/mattar88/auth_login_register_flutter_getx/main/screenshots/1_login.png" width="300"> | <img src="https://raw.githubusercontent.com/mattar88/auth_login_register_flutter_getx/main/screenshots/2_register.png" width="300"> |<img src="https://raw.githubusercontent.com/mattar88/auth_login_register_flutter_getx/main/screenshots/3_offline.png" width="300"> |

## Architecture 
 <img src="https://raw.githubusercontent.com/mattar88/auth_login_register_flutter_getx/main/screenshots/architecture.png" width="300">
 
 ``````
 #In this repository we will deposit our routes and pages. 
 - /routes
     # Contains the settings of pages(name Binding, midellwares,..).
     - app_pages.dart
     # Contains name of pages
     - app_routes.dart 
 #Bindings are classes where we can declare our dependencies and then 'bind' them to the routes page.    
 - /binding
     # In this binding inject the dependencies that used as soon as the app starts 
     contains ConnectivityServices to check if there is Internet Connectivity
     - app_binding.dart
     # We inject the home services api and the home controller
     - home_binding.dart 
     # We inject the login api services and the login controller
     - login_binding.dart
     # We inject the register api services and the signup controller
     - signup_binding.dart
 # In this repository we declare the middleware of routes    
 - /middlewares
     # This middleware is use by home route to check if there is an access token
     in the local storage before open the Home page or redirect to Login page
     - auth_middleware.dart
  # In this repository we declare the mixins classes where is the StateMixin and the common functionality
  # You can use the StateMixin to handle your UI state in a more efficient and clean way, when you perform asynchronous tasks
 - /mixins
     # We declare the helper class that contains common functionality that implement by multiple classes
     - helper_mixin.dart  
  #In this repository we declare the Controllers which responsible for controlling the application logic and acts as the coordinator between the Screens and the Models.   
 - /controllers
     # Responsible for signin and signup and share this functionality with login and signup controllers
     - auth_controller.dart  
     #Contains the logic and the functionality of home page
     - home_controller.dart  
     #Containes the logic of Login page(Form validations, sigin request and other) and inherit some functionality from auth controller
     - login_controller.dart  
     #Containes the logic of Login page and inherit some functionality from auth controller
     - signup_controller.dart.dart
  #In this repository we declare the Classes that represents the core information that application is being used to access and manipulate   
 - /models
     - home_model.dart  
     #Used by auht controller to represent the token loaded when login or register
     - token_model.dart
 #In this repository we declare the Classes that contains a widgets and data form widgets that produces a view to mobile screen or  browser
 - /screens
     - home_model.dart  
     #Used by auht controller to represent the token loaded when login or register
     - token_model.dart  
 ``````       
 
## Flutter Version
``````
PS > flutter --version
Flutter 2.10.1 • channel stable • https://github.com/flutter/flutter.git
Framework • revision db747aa133 (5 weeks ago) • 2022-02-09 13:57:35 -0600
Engine • revision ab46186b24
Tools • Dart 2.16.1 • DevTools 2.9.2

``````

## Change the project name
1. flutter clean
2. ``````Ctrl+Shift+F`````` then Search and replace all ``````auth_login_register_flutter_getx`````` with ``````NEW_PROJECT_NAME``````
3. Search for ``````auth_login_register_flutter_getx`````` in the project folder, and replace them with ``````NEW_PROJECT_NAME`````` one by one. Some of them are in the text files, make sure that you have changed them too.

## Installation
1. Download Flutter version mentioned above
2. Clone the project

3. Open`````` lib  > confi > config_api.dart`````` then set the variables

4. Open `````` lib > services > auth_api_service.dart``````  then set your REST API URL by changing the following variables
``````
 signUpUrl = '/api/user';
 signInUrl = '/oauth2/token';
 refreshTokenUrl = '/oauth2/token';
``````

