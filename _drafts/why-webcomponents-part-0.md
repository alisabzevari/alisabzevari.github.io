---
layout: post
title: Why web components - Part 0
---

Other programmers on the other side of the world probably 
made a new Javascript framework when you were sleeping last night. 
We obviously know that separating from the framework we are using 
currently is not easy for us (Although learning new things is the joy of programming).
Moreover it can turn into a nightmare when you think about the codes you
wrote with that old framework and planning to migrate to a new framework.
I have those feelings about AngularJS.

## The Curse of AngularJS
When I started working with AngularJS, I felt it is the solution of
the long lasting problem of creating web applications, Which was
struggling with DOM with an unstructured language. Besides other angular
problems, it has a wonderful talent of putting your code into its trap
(I am talking about `$http` and `$scope` and other angular specific concepts).
And after 3 years of working with this framework, when you start to 
triumph the success of your projects,
programmers which you read their blogs every day start to insult you 
with these words: performance, isolated scope, $digest, $interpolate etc.

## Dreaming of an ideal framework
This is the beginning of a series of thinking sessions which supposed 
to lead us to find what an ideal framework should have. In my personal
view, these items are some of the characteristics that an ideal
 framework should have:
 * There is no way to write and `ng-repeat` on multiple elements. 
	 Although the introduced `ng-repeat-start` and `ng-repeat-end` but
	 these directives are not what I was thinking it should be. I wanted
	 a dummy element which I could write `ng-repeat` on it. Aurelia
	 uses [`template` element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/template)
	 and it works well.
 * The DSL introduced for templating in angular is a bit awkward. I always need to look at other
 	examples and documentations of `ng-options` to write the correct syntax of it. Aurelia
	has a better approach in some parts. For example, it uses ES6 string interpolation 
	syntax instead of double curly braces. But react's solution beats all of the other
	templating languages which is not using any templating language. JSX, I believe, is 
	the best alternative to other templating languages. Think of writing an `ng-repeat`
	with a simple javascript `for` which is obviously more powerful!
 * There is a concept in angular called module but I doesn't help you to modularize your
 	web application! In my oppinion, modules must have the ability to be lazy loaded. But
	 there aren't any plans to load modules lazily in angular. Although oc-lazyload
 * dependency injection
 * ui router
 * $scope.$apply
 * $watch
 * directives
 * size
 * performance
 * 



counting the disadvantages of angular and start to search for a new framework
then eveywhere is a new framework!

## Angular and react showed the vision
react: being a library

angular: custom html elements



 