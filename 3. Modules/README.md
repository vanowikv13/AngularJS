# AngularJS Modules
Description:
1. An AngularJS module defines an application.
2. The module is a container for the different parts of an application.
3. The module is a container for the application controllers.
4. Controllers always belong to a module

### Creating a Module
A module is created by using the AngularJS function **angular.module**

```HTML
<div ng-app="myApp">...</div>
<script>
    var app = angular.module("myApp", []); 
</script>
```

The "myApp" parameter refers to an HTML element in which the application will run.

Now you can add controllers, directives, filters, and more to your AngularJS application.

### Ading Controller
Add a controller to your application, and refer to the controller with the ng-controller directive:

```HTML
<div ng-app="myApp" ng-controller="myCtrl">
    {{ firstName + " " + lastName }}
</div>

<script>
    var app = angular.module("myApp", []);

    app.controller("myCtrl", function($scope) {
        $scope.firstName = "John";
        $scope.lastName = "Doe";
    });
</script>
```

### Adding a Directive
AngularJS has a set of built-in directives which you can use to add functionality to your application.

In addition you can use the module to add your own directives to your applications:

```HTML
    <div ng-app="myApp" my-directive></div>

    <script> 
    var app = angular.module("myApp", []);

    app.directive("myDirective", function() {
        return {
            template : "My first directive woow"
        };
    });
    </script>
```

### Modules and Controllers in Files
It is common in AngularJS applications to put the module and the controllers in JavaScript files.

In this example, "myApp.js" contains an application module definition, while "myCtrl.js" contains the controller:

Example is in files.html, myApp.js, myCtrl.js

### At the end
While it is common in HTML applications to place scripts at the end of the <body> element, it is recommended that you load the AngularJS library either in the <head> or at the start of the <body>.

This is because calls to angular.module can only be compiled after the library has been loaded.