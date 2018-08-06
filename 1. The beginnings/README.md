# The beginnings with AngularJS
### Description
Angular extend HTML language with directives and expressions.

Angular JS is framework and library written in JS. It's distributed as JS file and can be added in script tag: 
```HTML
<script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.6.9/angular.min.js"></script>
```

**For newest version search in web.**

### AngularJS Directives
AngularJS extend HTML with *ng-directives*

The **ng-app** directives defines an AngularJS application.

The **ng-model** directive binds the value of HTML controls (input, select, textarea) to application data.

The **ng-bind** directive binds application data to HTML view.

```HTML
    <div ng-app="">
        <p>Name: <input type="text" ng-model="name"></p>
        <p ng-bind="name"></p>
    </div>
```

The **ng-app** directives tells AngularJS that the <div> element is the "owner" of tan AngularJS application.

The **ng-model** directives binds the value of the input field to the application variable name.

The **ng-bind** directive binds the content of the <p> element to the application variable name.

```HTML
    <div ng-app="" ng-init="firstName='John'">
        <p>The name is <span ng-bind="firstName"></span></p>
    </div>
```

The **ng-init** directive initialize AngularJS application variable.
ng-init="firstName='John'"

### AngularJS Expressions
AngularJS expression are written inside double braces **{{expression}}**
AngularJS will "output" data exactly where the expression is written.

AngularJS expressions bind AngularJS data to HTML the same way as the **ng-bind** directive.

```HTML
    <div ng-app="">
        <p>Name: <input type="text" ng-model="name"></p>
        {{name}}
    </div>
```

### AngularJS Applications:
AngularJS **modules** define AngularJS applications.
AngularJS **controller** control AngularJS applications.
The **ng-app** directive defines the application
The **ng-controller** directive defines the controller

```HTML
    <div ng-app="myApp" ng-controller="ctrl" ng-init="age:'17'">
        First Name: <input type="text" ng-model="firstName"><br>
        Last Name: <input type="text" ng-model="lastName"><br>
        <br>
        Full Name: {{firstName + " " + lastName}}

        <br><br>
        <p>Age: <input type="number" ng-model="age"></p>
        <p ng-bind="age"></p>
        {{age}}
    </div>

    <script>
        //The AngularJS module define application:
        var app = angular.module('myApp',[]);
        //AngularJS controller control applications:
        app.controller('ctrl',function($scope) {
            //here we define the proposal values that 
            //wil be from the beggining
            $scope.firstName = "Mariusz";
            $scope.lastName = "Nowicki";
            $scope.age = 1;
        });

    </script>
```

### At the end
I think that this technology have really big potential in future development see you next time my friend :)