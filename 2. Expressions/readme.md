# AngularJS Expressions
AngularJS binds data to HTML using **Expressions**

### AngularJS Expression
AngularJS expressions can be written inside:
1. {{expresssion}} - inside double braces
2. ng-bind="expression" - inside a directive

AngularJS will resolve the expression, and return the result exactly where the expession is written.

AngularJS expression are much like JS expression: They can contain literals, operators and variables.

Examples of expressions:
* {{5 + 5}}
* {{firstNmae + " " + secondName}}
* <p ng-bind="fav * fav"></p>

Example in code:
```HTML
    <div ng-app="">
        Favorite number: <input type="number" ng-model="fav">
        <p>{{fav * fav}}</p>
        <p ng-bind="fav * fav"></p>
    </div> 
```

**remember that if in this example you will delte ng-app="" the expression will be treat as normal text**
If you want to check how it's look just delete the line with ng-app="" in exmaple above.

You can write expressions wherever you like, AngularJS will simply resolve the expression and return the result.

Angular code can easily even chenge the value of css prophies:
```HTML
    <div ng-app="" ng-init="myCol='lightblue'">
        <input style="background-color:{{myCol}}" ng-model="myCol">
    </div>
```
### AngularJS Numbers
AngularJS number are like JS numbers:

Example with {{ expression }}:
```HTML
    <div ng-app="" ng-init="quantity=1;cost=5">
        <p>Total in dollar: {{ quantity * cost }}</p>
    </div>
```

Example with ng-bind:
```HTML
    <div ng-app="" ng-init="quantity=1;cost=5">
        <p>Total in dollar: <span ng-bind="quantity * cost"></span></p>
    </div>
```
### AngularJS Strings
AngularJS strings are like JS strings:

```HTML
    <div ng-app="">
        First Name: <input type="text" ng-model="firstName"><br>
        Second Name: <input type="text" ng-model="secondName"><br>
        <p>{{firstName + " " + secondName}}</p>
        <p ng-bind="firstName + " " + secondName"></p>
    </div>
```

### AngujarJS Objects
AngularJS objects are like JS objects:

```HTML
    <div ng-init="Animal={age:'4',name:'Reks'}">
       <p>My Animal name is {{Animal.name}} and his age is {{Animal.age}}</p>
       <p ng-bind="'My Animal name is ' + Animal.name + ' and his age is ' + Animal.age"></p>
    </div>
```

### AngularJS Arrays
AngularJS arrays are like JavaScript arrays:

```HTML
    <div ng-init="days = ['Monday', 'Thuesday', 'Wendsday', 'Thursday', 'Friday', 'Saturday', 'Sunday']">
        In witch day you are working: <input type="number" ng-model="dayNumber"><br>
        <p>{{days[dayNumber -1]}}</p>
        <p ng-bind="days[dayNumber - 1]"></p>
    </div>
```

### What I think?
I think for now everytihng is preaty simmple and we shouldn't stress about it :)