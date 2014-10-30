angular-markdown-filter
=======================

Markdown filter for Angular

## Installation
```bash
$ bower install angular-markdown-filter
```

## Import dependencies
```html
<script src="/bower_components/showdown/compressed/showdown.js"></script>
<script src="/bower_components/angular-markdown-filter/markdown.js"></script>
```
```javascript
angular.module('myApp', [
  'markdown'
]);
```

## Configuration
The underlying Showdown converter can be configured through the `markdown` provider
```javascript
angular.module('markdown')
  .config(function(markdownProvider) {
    markdownProvider.config({
      extensions: ['table']
    });
  });
``` 
see the [Showdown documentation](https://github.com/showdownjs/showdown#creating-markdown-extensions)
for details on how to create extensions.

## Usage
```javascript
angular.module('myApp')
  .controller('MainCtrl', function ($scope) {
    $scope.text = '# Heading 1';
  });
```
```html
<div class="container">{{ text | markdown }}</div>
```
