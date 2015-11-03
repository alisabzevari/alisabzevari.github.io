---
layout: post
title: The ultimate guide of converting strings to numbers in javascript
---
*In every programming language there are some tips which doesn't seem 
important. But being expert in that language undoubtedly 
related to knowing these small gotchas. I am going to learn and 
document them in javascript language and thereupon share here.*

The first time that converting strings to numbers in javascript
 catched my eye was when I noticed using a + before a variable.
 This is the 
 [definition of unary plus operator from MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Unary_plus_()):
> The unary plus operator precedes its operand and evaluates 
to its operand but attempts to converts it into a number, if it isn't 
already. Although unary negation (-) also can convert non-numbers, 
unary plus is the **fastest and preferred way of converting something
 into a number**, because it does not perform any other operations
  on the number. It can convert string representations of
   integers and floats, as well as the non-string values true, false
   , and null. Integers in both decimal and hexadecimal
    ("0x"-prefixed) formats are supported. Negative numbers
	 are supported (though not for hex). If it cannot parse a particular value, it will evaluate to NaN.

Here are some examples tested in chrome:

{% highlight js %}

+"1" // 1
+"-1" // -1
+"1.1" // 1.1
+"0xF" // 15

+"false" // NaN
+"true" // NaN
+"foo" // NaN

+"" // 0
+true // 1
+false // 0
+null // 0
+undefined // NaN

+(new Date()) // 1446550170891

{% endhighlight %}

There are other ways of converting strings to number and also
there are other functions which automatically convert strings to
numbers:

{% highlight js %}

parseInt("1000", 10) // 1000
Math.floor("1000.01") // 1000
Math.round("1000.01") // 1000
Math.round("1000.9") // 1001
parseFloat("1000.1") // 1000.1
Number("1000.1") // 1000.1

{% endhighlight %}

**Note 1:** Avoiding radix (2nd parameter) in `parseInt` could result
different in different implementations [[*]](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseInt).

**Note 2:** Double bitwise not (~~) can also convert string to its
representing number, but it could result strange for large numbers.
Actually, it will convert the string to 32bit integers and if the 
integer can not be represented in 32bits, it will wrap.

## References
* Stackoverflow - [[1]](http://stackoverflow.com/questions/1133770/how-do-i-convert-a-string-into-an-integer-in-javascript),
[[2]](http://stackoverflow.com/questions/221539/what-does-the-plus-sign-do-in-new-date)
* MDN - [[1]](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators),
[[2]](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseInt)
[[3]](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)
[[4]](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#Number_type)

