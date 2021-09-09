---
layout: post
title:  "SQL notes part 2"
date:   2021-08-20 12:32:32 -0700
categories: code notes
---

<h1>This is a cheatsheet for SQL String & Date manipulations</h1>

<h4>Extracting part of a string:</h4>
{% highlight SQL %}
SUBSTR(col_name, 4, 2)
{% endhighlight %}
This means start at position #4 and move right for 2 spaces.  The first position is #1.

<h4>Putting strings together:</h4>
{% highlight SQL %}
CONCAT(day_of_week, ',', LEFT(date, 10)) AS day_and_date
{% endhighlight %}
Or use || to "glue" together the parts without using CONCAT() function.

<h4>Changing letter case:</h4>
{% highlight SQL %}
UPPER()
LOWER()
{% endhighlight %}

<h4>Replace pattern:</h4>
{% highlight SQL %}
REPLACE(col_string, pattern, replacement)
{% endhighlight %}

<h4>Remove part of a string:</h4>
{% highlight SQL %}
trim(col_string, character)
{% endhighlight %}
The second argument is optional, if nothing explicit is given then spaces get removed.

<h4>Search within WHERE clause:</h4>
{% highlight SQL %}
SELECT cust_ID, cust_name, region
FROM customer
WHERE cust_ID LIKE '1-1%'
{% endhighlight %}
% works like a wild card

