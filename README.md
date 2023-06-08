## This repository is now considered legacy and no longer supported. It has been replaced with our latest Form Builder and Renderer @ https://github.com/formio/formio.js and Angular libraries @ https://github.com/formio/angular.
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fraesuarez%2FngFormBuilderTEST.svg?type=shield)](https://app.fossa.com/projects/git%2Bgithub.com%2Fraesuarez%2FngFormBuilderTEST?ref=badge_shield)


## Please take a look at our recent repositories and help documentation at the following links.
 - https://help.form.io
 - https://github.com/formio/formio.js
 - https://github.com/formio/formio
 - https://github.com/formio/react
 - https://github.com/formio/angular
 - https://github.com/formio/vue

The [Form.io](https://form.io) Form Builder
--------------------------------
This library provides form building capabilities to an Angular.js application. This form builder's purpose is to 
construct a JSON object reporesentation of a form, which could then be handed off to a Form Renderer such as the one
found @ [https://github.com/formio/ngFormio](https://github.com/formio/ngFormio).  The following landing page should
provide a good example of how this form builder works.

[See Working Example](http://codepen.io/travist/full/xVyMjo/)

The form builder can be embedded within your application using the following embed code.

```
<form-builder form="myform"></form-builder>
```

Where ```myform``` would be a form object that is placed on the scope of the controller containing the form builder.

Installation
================
To install this within your application, you will first need to include the following 


Adding Components
=================
To add a component, add it in the config phase.

```
  angular
    .module('myApp')
    .config([
      'formioComponentsProvider',
      function (formioComponentsProvider) {
        formioComponentsProvider.register('myfield', {
          title: 'My Field',
          template: 'formio/components/icons.html',
          controller: ['$scope', function($scope) {
          }],
          group: 'custom',
          icon: 'fa fa-heart-o',
          settings: {},
          views: []
        });
```
Removing Components
===================
To remove default components or groups from the form builder, set them as disabled in the run phase.

```
  angular.module('myApp')
    .run(['formioComponents', function(formioComponents) {
      formioComponents.components.textfield.disabled = true;
      formioComponents.groups.layout.disabled = true;
    }]);
```

Form.io
==============
This project is provided by [Form.io](https://form.io), which is a combined form and API platform for Developers.


## License
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fraesuarez%2FngFormBuilderTEST.svg?type=large)](https://app.fossa.com/projects/git%2Bgithub.com%2Fraesuarez%2FngFormBuilderTEST?ref=badge_large)