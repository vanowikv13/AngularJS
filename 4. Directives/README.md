# Directives
Description:
1. Let's you extend HTML with new attributes called **Directives**
2. AngularJS has a set of built-in directives which offers functionality to your applications.
3. Let's you also define your own directives

### AngularJS Directives
AngularJS directives are extended HTML attributes with the prefix ng-.

The ng-app directive initializes an AngularJS application.

The ng-init directive initializes application data.

The ng-model directive binds the value of HTML controls (input, select, textarea) to application data.

```HTML
    <div ng-app="" ng-init="PI=3.14">
        <p>{{ 4 * PI}}</p>s
    </div>
```

The ng-app directive also tell AngularJS that the <div> element is the "owner" of the AngularJS application.

### Data Binding
It means that we binds our data with some place in application

```HTML
<div ng-app="" ng-init="quantity=1;price=5">
    Quantity: <input type="number" ng-model="quantity">
    Costs:    <input type="number" ng-model="price">
Total in dollar: {{ quantity * price }}
</div>
```

### Repeating HTML Elements
The **ng-repeat** directive repeats an HTML element:
```HTML
    <div ng-app="" ng-init="names=['Jani','Hege','Kai']">
    <ul>
        <li ng-repeat="x in names">
        {{ x }}
        </li>
    </ul>
    </div>
```
The **ng-repeat** directive actually clones HTML elements once for each item in a collection.

The ng-repeat directive used on an array of objects:
```HTML
<div ng-app="" ng-init="names=[
{name:'Jani',country:'Norway'},
{name:'Hege',country:'Sweden'},
{name:'Kai',country:'Denmark'}]">
    <ul>
        <li ng-repeat="x in names">
            {{ x.name + ', ' + x.country }}
        </li>
    </ul>
</div>
```

### The ng-app Directive
1. Define the **root element** the app.
2. It will **auto-bootstrap** (automatically initialize) the app when a web page is loaded.

### The ng-init Directive
1. Defines **initial value** for the app.
2. Normally, you will not use ng-init. You will use a controller or module instead.

### The ng-model Directive
It Binds the value of HTML controls (input, select, textarea) to app data.
The ng-model directive can also:
* Provide type validation for application data (number, email, required).
* Provide status for application data (invalid, dirty, touched, error).
* Provide CSS classes for HTML elements.
* Bind HTML elements to HTML forms.

### Create New Directives
In addition to all the built-in AngularJS directives, you can create your own directives.

New directives are created by using the **.directive** function.

To invoke the new directive, make an HTML element with the same tag name as the new directive.

When naming a directive, you must use a camel case name, MyOwnDirective, but when invoking it, you must use - separated name, my-own-directive:

```HTML
<body ng-app="myApp">
    <my-own-directive></my-own-directive>
        
    <script>
        var app = angular.module("myApp", []);
        app.directive("myOwnDirective", function() {
            return {
                template : "<h1>Made by a directive!</h1>"
            };
        });
    </script>
</body>
```

You can invoke a directive by using:
* Element name
```HTML
    <my-own-directive></my-own-directive>
```
* Attribute
```HTML
    <div my-own-directive></div>
```
* Class
```HTML
    <div class="my-own-directive"></div>
```
* Comment
```HTML
    <!-- directive: w3-test-directive -->
```

### Restrictions
You can restrict your directives to only be invoked by some of the methods.

By adding a restrict property with the value "A", the directive can only be invoked by attributes:
```JS
    var app = angular.module("myApp", []);
    app.directive("w3TestDirective", function() {
        return {
            restrict : "A",
            template : "<h1>Made by a directive!</h1>"
        };
    });
```

The legal restrict values are:
* **E** for Element name
* **A** for Attribute
* **C** for Class
* **M** for Comment

By default the value is EA, meaning that both Element names and attribute names can invoke the directive.