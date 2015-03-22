# ng-simple-dialog

A simple, yet powerful dialog utility for [AngularJS](https://angularjs.org). Based on [simple-dialog](https://github.com/nikku/simple-dialog).


## Usage

Include the module into your application:

```javascript
var myModule = angular.module('myModule', [
  require('ng-simple-dialog')
]);
```

Create dialogs anywhere, i.e. in controllers:


```javascript
var dialogTemplate =
  '{{ a }} + {{ b }} <br/>' +
  '<button ng-click="dialog.close(a + b)">CALCULATE</button>';


function MyController($scope, ngSimpleDialog) {

  var data = {
    a: 'A',
    b: 'B'
  };

  this.openDialog = function() {

    var dialog = ngSimpleDialog({
      template: dialogTemplate,
      scope: data
    });

    dialog.open().on('close', function(resultValue) {
      data.resultValue = resultValue
    });
  };
}
```


## License

MIT