---
layout: post
title:  Simple social sharing in Jekyll
date:   2016-02-26 12:17:00
author: Matthew Shaw
image:  
tags:
- Jekyll
- FontAwesome
- Bootstrap
- Facebook
- Twitter
- Google
---
I wanted to add social media sharing buttons to my [Jekyll](http://jekyllrb.com/) powered blog (this one!) but I didn't want the styling enforced by the various social networks' own buttons, or their inline JavaScript.

I also wanted to turn all the tags on a post into hashtags on a tweet. This was easily achieved by adding the following parameter to the [tweet web intent](https://dev.twitter.com/web/tweet-button/web-intent) URL: {% raw %}```&hashtags={% for tag in page.tags %}{{tag}},{% endfor %}```{% endraw %}

Let's keep it simple, no JavaScript required, just [Bootstrap](http://getbootstrap.com/) and [FontAwesome](http://fontawesome.io/), with all existing styling retained. Please remember to share this post too using any of the links below!

---

#### **Icon Links**

##### Twitter:
<a href="https://twitter.com/intent/tweet?text={{page.title}}:&url={{site.url}}{{page.url}}&via={{site.twitter_username}}&related={{site.twitter_related}}&hashtags={% for tag in page.tags %}{{tag}},{% endfor %}" rel="nofollow" target="_blank"><i class="fa fa-twitter-square fa-fw fa-3x"></i></a>

{% highlight html %}
{% raw %}
<a href="https://twitter.com/intent/tweet?text={{page.title}}:&url={{site.url}}{{page.url}}&via={{site.twitter_username}}&related={{site.twitter_related}}&hashtags={% for tag in page.tags %}{{tag}},{% endfor %}" rel="nofollow" target="_blank"><i class="fa fa-twitter-square fa-fw fa-3x"></i></a>
{% endraw %}
{% endhighlight %}


##### Facebook:
<a href="https://facebook.com/sharer.php?u={{ site.url }}{{ page.url }}" rel="nofollow" target="_blank"><i class="fa fa-facebook-square fa-fw fa-3x"></i></a>

{% highlight html %}
{% raw %}
<a href="https://facebook.com/sharer.php?u={{ site.url }}{{ page.url }}" rel="nofollow" target="_blank"><i class="fa fa-facebook-square fa-fw fa-3x"></i></a>
{% endraw %}
{% endhighlight %}


##### Google+:
<a href="https://plus.google.com/share?url={{ site.url }}{{ page.url }}" rel="nofollow" target="_blank"><i class="fa fa-google-plus-square fa-fw fa-3x"></i></a>

{% highlight html %}
{% raw %}
<a href="https://plus.google.com/share?url={{ site.url }}{{ page.url }}" rel="nofollow" target="_blank"><i class="fa fa-google-plus-square fa-fw fa-3x"></i></a>
{% endraw %}
{% endhighlight %}

---

#### **Buttons**

##### Twitter:
<p><a class="btn btn-default" href="https://twitter.com/intent/tweet?text={{page.title}}:&url={{site.url}}{{page.url}}&via={{site.twitter_username}}&related={{site.twitter_related}}&hashtags={% for tag in page.tags %}{{tag}},{% endfor %}" rel="nofollow" target="_blank"><i class="fa fa-twitter fa-fw fa-lg"></i> Twitter</a></p>

{% highlight html %}
{% raw %}
<p><a class="btn btn-default" href="https://twitter.com/intent/tweet?text={{page.title}}:&url={{site.url}}{{page.url}}&via={{site.twitter_username}}&related={{site.twitter_related}}&hashtags={% for tag in page.tags %}{{tag}},{% endfor %}" rel="nofollow" target="_blank"><i class="fa fa-twitter fa-fw fa-lg"></i> Twitter</a></p>
{% endraw %}
{% endhighlight %}


##### Facebook:
<p><a class="btn btn-default" href="https://facebook.com/sharer.php?u={{ site.url }}{{ page.url }}" rel="nofollow" target="_blank"><i class="fa fa-facebook fa-fw fa-lg"></i> Facebook</a></p>

{% highlight html %}
{% raw %}
<p><a class="btn btn-default" href="https://facebook.com/sharer.php?u={{ site.url }}{{ page.url }}" rel="nofollow" target="_blank"><i class="fa fa-facebook fa-fw fa-lg"></i> Facebook</a></p>
{% endraw %}
{% endhighlight %}


##### Google+:
<p><a class="btn btn-default" href="https://plus.google.com/share?url={{ site.url }}{{ page.url }}" rel="nofollow" target="_blank"><i class="fa fa-google-plus fa-fw fa-lg"></i> Google+</a></p>

{% highlight html %}
{% raw %}
<p><a class="btn btn-default" href="https://plus.google.com/share?url={{ site.url }}{{ page.url }}" rel="nofollow" target="_blank"><i class="fa fa-google-plus fa-fw fa-lg"></i> Google+</a></p>
{% endraw %}
{% endhighlight %}

---

#### **Panels**

You might want to group the social sharing links in a panel, or other visual carrier, as I have done on this site. Place them in appropriate row/column grid classes to suit your own layout.

##### Icon Link Panel:

<div class="row">
  <div class="col-xs-12 col-sm-4">
    <div class="panel panel-default">
      <div class="list-group">
        <div class="list-group-item">
          <h5 class="list-group-item-heading"><i class="fa fa-share-alt fa-fw"></i> Share</h5>
        </div>
        <div class="list-group-item">
          <a href="https://twitter.com/intent/tweet?text={{page.title}}:&url={{site.url}}{{page.url}}&via={{site.twitter_username}}&related={{site.twitter_related}}&hashtags={% for tag in page.tags %}{{tag}},{% endfor %}"
          rel="nofollow" target="_blank">
          <i class="fa fa-twitter-square fa-fw fa-3x"></i></a>
          <a href="https://facebook.com/sharer.php?u={{ site.url }}{{ page.url }}"
          rel="nofollow" target="_blank">
          <i class="fa fa-facebook-square fa-fw fa-3x"></i></a>
          <a href="https://plus.google.com/share?url={{ site.url }}{{ page.url }}"
          rel="nofollow" target="_blank">
          <i class="fa fa-google-plus-square fa-fw fa-3x"></i></a>
        </div>
      </div>
    </div>
  </div>
</div>

{% highlight html%}
{% raw %}
<div class="row">
  <div class="col-xs-12 col-sm-4">
    <div class="panel panel-default">
      <div class="list-group">
        <div class="list-group-item">
          <h5 class="list-group-item-heading"><i class="fa fa-share-alt fa-fw"></i> Share</h5>
        </div>
        <div class="list-group-item">
          <a href="https://twitter.com/intent/tweet?text={{page.title}}:&url={{site.url}}{{page.url}}&via={{site.twitter_username}}&related={{site.twitter_related}}&hashtags={% for tag in page.tags %}{{tag}},{% endfor %}"
          rel="nofollow" target="_blank">
          <i class="fa fa-twitter-square fa-fw fa-3x"></i></a>
          <a href="https://facebook.com/sharer.php?u={{ site.url }}{{ page.url }}"
          rel="nofollow" target="_blank">
          <i class="fa fa-facebook-square fa-fw fa-3x"></i></a>
          <a href="https://plus.google.com/share?url={{ site.url }}{{ page.url }}"
          rel="nofollow" target="_blank">
          <i class="fa fa-google-plus-square fa-fw fa-3x"></i></a>
        </div>
      </div>
    </div>
  </div>
</div>
{% endraw %}
{% endhighlight %}

##### Button Panel:

Buttons have the `btn-block` class added to expand them to the panel width.

<div class="row">
  <div class="col-xs-12 col-sm-4">
    <div class="panel panel-default">
      <div class="list-group">
        <div class="list-group-item">
          <h5 class="list-group-item-heading"><i class="fa fa-share-alt fa-fw"></i> Share</h5>
        </div>
        <div class="list-group-item">
          <p><a class="btn btn-default btn-block" href="https://twitter.com/intent/tweet?text={{page.title}}:&url={{site.url}}{{page.url}}&via={{site.twitter_username}}&related={{site.twitter_related}}&hashtags={% for tag in page.tags %}{{tag}},{% endfor %}"
          rel="nofollow" target="_blank">
          <i class="fa fa-twitter fa-fw fa-lg"></i> Twitter</a></p>
          <p><a class="btn btn-default btn-block" href="https://facebook.com/sharer.php?u={{ site.url }}{{ page.url }}"
          rel="nofollow" target="_blank">
          <i class="fa fa-facebook fa-fw fa-lg"></i> Facebook</a></p>
          <p><a class="btn btn-default btn-block" href="https://plus.google.com/share?url={{ site.url }}{{ page.url }}"
          rel="nofollow" target="_blank">
          <i class="fa fa-google-plus fa-fw fa-lg"></i> Google+</a></p>
        </div>
      </div>
    </div>
  </div>
</div>

{% highlight html%}
{% raw %}
<div class="row">
  <div class="col-xs-12 col-sm-4">
    <div class="panel panel-default">
      <div class="list-group">
        <div class="list-group-item">
          <h5 class="list-group-item-heading"><i class="fa fa-share-alt fa-fw"></i> Share</h5>
        </div>
        <div class="list-group-item">
          <p><a class="btn btn-default btn-block" href="https://twitter.com/intent/tweet?text={{page.title}}:&url={{site.url}}{{page.url}}&via={{site.twitter_username}}&related={{site.twitter_related}}&hashtags={% for tag in page.tags %}{{tag}},{% endfor %}"
          rel="nofollow" target="_blank">
          <i class="fa fa-twitter fa-fw fa-lg"></i> Twitter</a></p>
          <p><a class="btn btn-default btn-block" href="https://facebook.com/sharer.php?u={{ site.url }}{{ page.url }}"
          rel="nofollow" target="_blank">
          <i class="fa fa-facebook fa-fw fa-lg"></i> Facebook</a></p>
          <p><a class="btn btn-default btn-block" href="https://plus.google.com/share?url={{ site.url }}{{ page.url }}"
          rel="nofollow" target="_blank">
          <i class="fa fa-google-plus fa-fw fa-lg"></i> Google+</a></p>
        </div>
      </div>
    </div>
  </div>
</div>
{% endraw %}
{% endhighlight %}
