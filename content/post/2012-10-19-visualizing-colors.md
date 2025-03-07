---
categories:
- rstats
date: 2012-10-19T00:00:00Z
tags:
- Graphics
title: Visualizing colors()

---

<p>The other day I learnt about the existance of the colors() vector in R which specifies all the character-based colors like &#8220;light blue&#8221;, &#8220;black&#8221;, etc. So I made a simple plot to visualize them all. Here&#8217;s the code:</p>


```r
mat <- matrix(1:length(colors()), ncol = 9, byrow= TRUE)
df <- data.frame(col = colors(), 
	x = as.integer(cut(1:length(colors()), 9)),
	y = rep(1:73, 9), stringsAsFactors=FALSE)
plot(y ~ jitter(x), data = df, col = df$col,
 	pch=16, main = "Visualizing colors() split in 9 groups",
 	xlab = "Group", 
	ylab = "Element of the group (min = 1, max = 73)",
	sub = "x = 3, y = 1 means that it's the 2 * 73 + 1 = 147th color")
```

<p>And the plot:</p>
<p><img src="http://media.tumblr.com/tumblr_mc5ovbt4uQ1qfs0hy.png"/></p>
