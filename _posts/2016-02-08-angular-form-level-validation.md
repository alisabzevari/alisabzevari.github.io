---
layout: post
title: AngularJS form level validation
---

AngularJS has done a good job in form related scenarios. One of the best parts is its validation. On the other side, one of the missing pieces in this area in form level validation. Although in one of the closed [issues](https://github.com/angular/angular.js/issues/631) in angular's github page Igor Minar mentioned that form level validation is addressed in 3rd forms rewrite. But I couldn't find anything useful. I have written a simple directive to address this issue:

{% gist 3703cca04d8aa6af559c angular-form-level-validation.js %}

The directive is very simple. It reads an object that its keys are validator names and its values are functions which should return boolean after doing validation. [This fiddle](https://jsfiddle.net/alisabzevari/q2ye6zyf/) is a sample for that directive.
