---
layout: post
title: An easy way to find duplicates in an array
---

I was fiddling with my blog. Here is a simple puzzle solution which was finding a duplicate in an array.
Array has only one duplicate in it. An easy solution is to use `indexOf` and
`lastIndexOf` in Javascript.

Here is my `findDuplicates` function:

{% highlight js %}
function findDuplicate(array){
  console.log(array.length);
  for (var i = 0; i < array.length; i++) {
    if (array.indexOf(array[i]) != array.lastIndexOf(array[i]))
      console.log(array[i]);
  }
}
{% endhighlight %}
