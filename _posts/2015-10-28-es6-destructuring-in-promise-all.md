---
layout: post
title: Using ES2015 destructuring to get rid of Promise.all annoyance
---

There were times when I refused to use `$q.all` in angularjs because
processing the result of promises in an array is suffering.

{% highlight js %}
let promises = [p1(), p2(), p3()];
$q.all(promises)
  .then(function (result) {
	  let p1Result = result[0];
	  let p2Result = result[1];
	  let p3Result = result[2];
	  // ...
  });
{% endhighlight %}

Using array to get the result of 3 promises that have names is a little
awkward. Furthermore, Having the results of 3 different promises in a single array
and referencing each of them with an index is not a clean way of coding. 

Today I found a solution to end this suffering by using new
ES2015 feature called destructuring. To know destructuring more and learn
other use cases you can read 
[Scott Alen's nice post](http://odetocode.com/blogs/scott/archive/2014/09/11/features-of-es6-part-6-destructuring.aspx) 
about it. Using destructuring, the above code will be:

{% highlight js %}
var promises = [p1(), p2(), p3()];
$q.all(promises)
  .then(function ([p1Result, p2Result, p3Result]) {
	  // ...
  });
{% endhighlight %}

As you can see, the result is more concise and readable. ES6 (ES2015)
has a lot of cool features.

Enjoy javascripting!