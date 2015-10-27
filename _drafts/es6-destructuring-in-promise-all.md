---
layout: post
title: Using ES6 destructuring to get rid of Promise.all annoyance
---

There were times when I refused to use `$q.all` in angularjs because
processing the result of promises in an array is suffering.

{% highlight js %}
```
var promises = [p1(), p2(), p3()];
$q.all(promises)
  .then(function (result) {
	  var p1Result = result[0];
	  var p2Result = result[1];
	  var p3Result = result[2];
  });
```
{% endhighlight %}

Using array to get the result of 3 promises that have names is a little
awkward. Having the results of 3 different promises in a single array
and referencing each of them with and index is not a clean way of coding. 

Today I found a solution to end this suffering and it is using new
ES6 feature called destructuring. To know destructuring more and learn
other use cases you can read 
[Scott Alen's nice post](http://odetocode.com/blogs/scott/archive/2014/09/11/features-of-es6-part-6-destructuring.aspx) 
about it. Using destructuring, the above code will be:
