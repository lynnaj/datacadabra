---
layout: post
title:  "Simple Data Analysis"
date:   2020-11-05 20:49:32 -0700
categories: Data Analysis
---

Let's say you sell a cool widget to tons of customers online and sales went up this month!  You have no idea how?  You wonder what changed to drive growth?  I have an analysis framework to help you find out!

1. List out features of your customers.  For example:
* Location (by region or country)
* Traffic origination (e.g. online ads, direct to website)
* Platform (mobile vs. web)
* Customer type (older vs. new, or other categories depending on your business model)
* Product type if there are more than 1 product


2. Look at growth percentage by each of the categories for each of the above features.  In the below example, I will analyze sales growth by platform.

3. Repeat the same analysis for other features.  In the case of location, you may have to join with Customers table to get the location data.  

The example - by platform type, find out if there have been an uptick in sales.  Here is a likely SQL query to look up sales by platform for the current month.  
{% highlight SQL %}
SELECT platform, SUM(price) AS current_total_sales
FROM Orders
GROUP BY platform
WHERE MONTH(date) = 11 AND
YEAR(date) = 2020
{% endhighlight %}

Then do the same thing for the previous month.  Calculate growth percent using 100*(current month sales - previous month sales)/previous month sales.

{% highlight SQL %}
SELECT 
current_month.platform, 
current_month.current_total_sales, 
previous_month.previous_total_sales, 
100*(current_month.current_total_sales-previous_month.previous_total_sales)/
previous_month.previous_total_sales AS growth
FROM
	(SELECT platform, SUM(price) AS current_total_sales
	FROM Orders
	GROUP BY platform
	WHERE MONTH(date) = 11 AND
	YEAR(date) = 2020) AS current_month
JOIN
	(SELECT platform, SUM(price) AS previous_total_sales
	FROM Orders
	GROUP BY platform
	WHERE MONTH(date) = 10 AND
	YEAR(date) = 2020) AS previous_month
ON current_month.platform = previous_month.platform
{% endhighlight %}




