---
permalink: /blogs/a-post-with-a-video
layout: post
title:  "A Post with a Video(유투브 비디오 넣는 예제)"
date:   2016-03-15
excerpt: "Custom written post descriptions are the way to go... if you're not lazy."
feature: http://i.imgur.com/Ds6S7lJ.png
tag:
- sample
- post
- video
- blog
blog: true
comments: true
---
<iframe width="560" height="315" src="//www.youtube.com/embed/SU3kYxJmWuQ" frameborder="0"> </iframe>

Video embeds are responsive and scale with the width of the main content block with the help of [FitVids](http://fitvidsjs.com/).

Not sure if this only effects Kramdown or if it's an issue with Markdown in general. But adding YouTube video embeds causes errors when building your Jekyll site. To fix add a space between the `<iframe>` tags and remove `allowfullscreen`. Example below:

{% highlight html %}
<iframe width="560" height="315" src="//www.youtube.com/embed/SU3kYxJmWuQ" frameborder="0"> </iframe>
{% endhighlight %}
