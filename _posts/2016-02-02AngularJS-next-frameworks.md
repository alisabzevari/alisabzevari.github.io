---
layout: post
title: My problems with AngularJS and what I think about next the generation web frameworks
---

Other programmers on the other side of the world probably made a new Javascript framework when you were sleeping last night. We obviously know that separating from the framework we are using currently is not easy for us (Although learning new things is the joy of programming). Moreover it can turn into a nightmare when you think about the codes you wrote with that old framework and planning to migrate them to a new framework. I have those feelings about AngularJS.

## The Curse of AngularJS
When I started working with AngularJS, I felt it is the solution of the long lasting problem of creating web applications, which was struggling with DOM with an unstructured language. Besides other angular problems, it has a wonderful talent of putting your code into its trap (I am talking about `$http` and `$scope` and other angular specific concepts). And after more than 3 years of building real world applications with this framework, once you start to celebrate the success of your project, programmers who you read their blogs every day start to insult you with these words: performance, isolated scope, `$digest`, `$interpolate` etc.

## Dreaming of an ideal framework
This is the beginning of a series of thinking sessions which supposed to lead us to find what an ideal framework should be. These critics about angularjs can lead us to some of the characteristics that an ideal framework should have:

1. There is no way to write an `ng-repeat` on multiple elements. Although they introduced `ng-repeat-start` and `ng-repeat-end` but these directives are not what I was thinking it should be. I wanted a dummy element which I could write `ng-repeat` on it. [Aurelia][aurelia] uses html's [`template`] [1] element and it works well.
2. The DSL introduced for view templates in angular is a bit awkward. For instance, I always need to look at examples and documentations of `ng-options` to write the correct syntax of it. Aurelia has a better approach in some parts. For example, it uses ES6 string interpolation syntax instead of double curly braces. But react's solution beats all of the other templating languages because it is not using any templating language at all. JSX, I believe, is the best alternative to other templating languages. Think of writing an `ng-repeat` with a simple JavaScript `for` which is obviously more powerful! 
3. There is a concept in angular called _module_, but I doesn't help you to build a modular web application! In my opinion, modules in a web application must have the ability to be lazy loaded. But there aren't any plans to load modules lazily in angular. Although [ocLazyLoad][2] tries to solve this problem but in cost of hacking angular. Fortunately, ES6's universal module definition tied all of the inventions in this area together. Using tools like [jspm][jspm] or [webpack][webpack], one can bundle related parts of an application together and create multiple lazy loadable modules. You can see benefits of this new language feature in the upcoming frameworks such as Aurelia and Angular 2 and even in react.
4. Angular was one of the first libraries which payed much attention to dependency injection but the implementation was very primitive and tricky. Although I can not blame angular for that because of the language weaknesses. Thinking in OOP paradigm, the best way to inject dependencies is through a class's constructor. Additionally, it is very important to decouple your business logic layer from framework. having `$inject` in all of the business layer objects or using `$scope.$apply` couples them more to angular. Decorators in ES2015 will help us to implement good IOC containers in JavaScript way while not cluttering the code or make it dependent to a specific framework. 
5. Angular has a zone which entering to it needs you to run `$scope.$apply`. It is the source of many misunderstandings and bugs when integrating a 3rd party library to angular.
6. Having 2 way data binding in angular achieved with the cost of performance and adding strange phases and cycles in angular. Angular 2 and Aurelia followed different approaches to tackle these problems. 
7. When it comes to directives you need to understand almost all of the angular internals to be able to write a good directive. In my opinion, [web components][webcomponents] is the answer to long lasting problem of components in html.
8. Although angular is a very productive framework but its size and the problem of lazy loading in its modules made it unusable in small applications and applications which make use of too many 3rd party libraries. [RiotJS][3] in size beats all of the other libraries.
I try to find a framework or a set of libraries to gather a suite of tools that don't have these issues.

## Angular and react showed the vision
In my opinion, the most important factor of Angular's popularity is directives. Directives made new expectations from HTML views. It made the MVC pattern more powerful by bringing the components on the table. People start to think of HTML as an structure which describes the relation between different components and a way to configure them. Elements are components. Sibling elements of a component are a way to modify a component's contents. Attributes are a way to configure components or talk with them. Another brilliant idea is that directives can be applied to attributes and classes to add generalized behavior to other components. For example, adding a tooltip to an element.

On the other hand, the brilliance of react is that it is not a framework. React didn't have assumptions about how do you implement other concerns like dependency injection, http services, business logic layer, routing etc. React is just a way to create components and creating components was always an important issue in web development.

In conclusion, my personal thinking is that we need to establish a standard for creating components in web and easily wrap components created with other frameworks and libraries like JQuery UI or Kendo UI. I don't think if react could be a good answer because it is not going to be a native API in web and it is not easy to integrate its components with other frameworks. But I think Web Components has a proper road map to fix this issue.

 [1]: https://developer.mozilla.org/en-US/docs/Web/HTML/Element/template
 [2]: https://oclazyload.readme.io/
 [3]: http://riotjs.com/
 [aurelia]: http://aurelia.io
 [jspm]: http://jspm.io/
 [webpack]: https://webpack.github.io/
 [webcomponents]: http://webcomponents.org/