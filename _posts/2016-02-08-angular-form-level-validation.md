---
layout: post
title: AngularJS form level validation
---

AngularJS has done a good job in form related scenarios. One of the best parts is its validation. On the other side, one of the missing pieces in this area in form level validation. Although in one of the closed [issues](https://github.com/angular/angular.js/issues/631) in angular's github page Igor Minar mentioned that form level validation is addressed in 3rd forms rewrite. But I couldn't find anything useful. I have written a simple directive to address this issue:
{% gist cf40015076b90f9b1860 angular-form-level-validation.ts %}