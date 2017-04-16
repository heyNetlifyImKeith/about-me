---
layout: post
title: Site Setup
excerpt: "A fun proccess with just a few hiccups."
categories: [building, problem solving]
comments: true
---
### Welcome to the proccess.

When I went to start this project I decided to use Jekyll as my Static Site Generator. The reason being simply because of its age and popularity. I figured that if I were to run into issues there will be quite a bit of information out there on how to solve it.

I did not want the site to be the default theme so I found one suitable to my liking and discovered gem themes! I had no idea that theming jekyll could be as simple as requiring a gem. Pretty cool.

##### A build issue.

After linking netlify to my github repo, the first couple deploys failed. After looking over the log I noticed there was a build script error.
{% highlight build %}
  Error running command: Build script returned non-zero exit code: 127
{% endhighlight %}
A few lines above that revealed that the jekyll command was not found.
{% highlight build %}
/opt/build/build.sh: line 406: jekyll: command not found
{% endhighlight %}
This tells me that more than likely jekyll is not being installed before the build. Sure enough I noticed my Gemfile was practicing it's greatest trick, the disappearing act. The solution was simple enough find where in the world that Gemfile went or in my case. Make a new one. After creating the Gemfile and populating it, the build succeeded!