---
layout: post
title:  Simple social media in Jekyll
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
- LinkedIn
---
I wanted to add social media share buttons to my [Jekyll](http://jekyllrb.com/) powered blog (this one!) but I didn't want the styling enforced by the various social networks' own buttons, or their inline JavaScript.

I also wanted to turn all the tags on a post into hashtags on a tweet. This was easily achieved by adding the following parameter to the [tweet web intent](https://dev.twitter.com/web/tweet-button/web-intent) URL: {% raw %}```&hashtags={% for tag in page.tags %}{{tag}},{% endfor %}```{% endraw %}

Let's keep it simple, no JavaScript required, just [Bootstrap](http://getbootstrap.com/) and [FontAwesome](http://fontawesome.io/). Please remember to share this post too using any of the links below!

---

#### **Brand Colours**

If you want to use the brands' own corporate colours / identity then you can apply the following css classes to your icons or buttons:

{% highlight css %}
.twitter {
  color: #55acee;
}
.facebook {
  color: #3b5998;
}
.google-plus {
  color: #dc4e41;
}
.linkedin {
  color: #0077b5;
}
{% endhighlight %}

---

#### **Font Awesome Icons**

Font Awesome has a wide variety of social media icons, either just the logo or inside rounded square carriers. We can also use the ability to stack icons and invert them to create new combinations of logos and carriers. Here's a few I've come up with:

<table class="table table-responsive">
  <thead>
    <tr>
      <th></th>
      <th>Solo</th>
      <th>Square</th>
      <th>Square Alt</th>
      <th>Square Outline</th>
      <th>Circle</th>
      <th>Circle Outline</th>
      <th>Circle Thin</th>
      <th>Comment</th>
      <th>Comment Outline</th>
    </tr>
  </thead>
  <tbody>
    <tr class="twitter">
      <td>Twitter</td>
      <td><i class="fa fa-twitter fa-lg"></i></td>
      <td><i class="fa fa-twitter-square fa-lg"></i></td>
      <td><span class="fa-stack fa-lg">
        <i class="fa fa-square fa-stack-2x"></i>
        <i class="fa fa-twitter fa-stack-1x fa-inverse"></i>
      </span></td>
      <td><span class="fa-stack fa-lg">
        <i class="fa fa-square-o fa-stack-2x"></i>
        <i class="fa fa-twitter fa-stack-1x"></i>
      </span></td>
      <td><span class="fa-stack fa-lg">
        <i class="fa fa-circle fa-stack-2x"></i>
        <i class="fa fa-twitter fa-stack-1x fa-inverse"></i>
      </span></td>
      <td><span class="fa-stack fa-lg">
        <i class="fa fa-circle-o fa-stack-2x"></i>
        <i class="fa fa-twitter fa-stack-1x"></i>
      </span></td>
      <td><span class="fa-stack fa-lg">
        <i class="fa fa-circle-thin fa-stack-2x"></i>
        <i class="fa fa-twitter fa-stack-1x"></i>
      </span></td>
      <td><span class="fa-stack fa-lg">
        <i class="fa fa-comment fa-stack-2x"></i>
        <i class="fa fa-twitter fa-stack-1x fa-inverse"></i>
      </span></td>
      <td><span class="fa-stack fa-lg">
        <i class="fa fa-comment-o fa-stack-2x"></i>
        <i class="fa fa-twitter fa-stack-1x"></i>
      </span></td>
    </tr>
    <tr class="facebook">
      <td>Facebook</td>
      <td><i class="fa fa-facebook fa-lg"></i></td>
      <td><i class="fa fa-facebook-square fa-lg"></i></td>
      <td><span class="fa-stack fa-lg">
        <i class="fa fa-square fa-stack-2x"></i>
        <i class="fa fa-facebook fa-stack-1x fa-inverse"></i>
      </span></td>
      <td><span class="fa-stack fa-lg">
        <i class="fa fa-square-o fa-stack-2x"></i>
        <i class="fa fa-facebook fa-stack-1x"></i>
      </span></td>
      <td><span class="fa-stack fa-lg">
        <i class="fa fa-circle fa-stack-2x"></i>
        <i class="fa fa-facebook fa-stack-1x fa-inverse"></i>
      </span></td>
      <td><span class="fa-stack fa-lg">
        <i class="fa fa-circle-o fa-stack-2x"></i>
        <i class="fa fa-facebook fa-stack-1x"></i>
      </span></td>
      <td><span class="fa-stack fa-lg">
        <i class="fa fa-circle-thin fa-stack-2x"></i>
        <i class="fa fa-facebook fa-stack-1x"></i>
      </span></td>
      <td><span class="fa-stack fa-lg">
        <i class="fa fa-comment fa-stack-2x"></i>
        <i class="fa fa-facebook fa-stack-1x fa-inverse"></i>
      </span></td>
      <td><span class="fa-stack fa-lg">
        <i class="fa fa-comment-o fa-stack-2x"></i>
        <i class="fa fa-facebook fa-stack-1x"></i>
      </span></td>
    </tr>
    <tr class="google-plus">
      <td>Google+</td>
      <td><i class="fa fa-google-plus fa-lg"></i></td>
      <td><i class="fa fa-google-plus-square fa-lg"></i></td>
      <td><span class="fa-stack fa-lg">
        <i class="fa fa-square fa-stack-2x"></i>
        <i class="fa fa-google-plus fa-stack-1x fa-inverse"></i>
      </span></td>
      <td><span class="fa-stack fa-lg">
        <i class="fa fa-square-o fa-stack-2x"></i>
        <i class="fa fa-google-plus fa-stack-1x"></i>
      </span></td>
      <td><span class="fa-stack fa-lg">
        <i class="fa fa-circle fa-stack-2x"></i>
        <i class="fa fa-google-plus fa-stack-1x fa-inverse"></i>
      </span></td>
      <td><span class="fa-stack fa-lg">
        <i class="fa fa-circle-o fa-stack-2x"></i>
        <i class="fa fa-google-plus fa-stack-1x"></i>
      </span></td>
      <td><span class="fa-stack fa-lg">
        <i class="fa fa-circle-thin fa-stack-2x"></i>
        <i class="fa fa-google-plus fa-stack-1x"></i>
      </span></td>
      <td><span class="fa-stack fa-lg">
        <i class="fa fa-comment fa-stack-2x"></i>
        <i class="fa fa-google-plus fa-stack-1x fa-inverse"></i>
      </span></td>
      <td><span class="fa-stack fa-lg">
        <i class="fa fa-comment-o fa-stack-2x"></i>
        <i class="fa fa-google-plus fa-stack-1x"></i>
      </span></td>
    </tr>
    <tr class="linkedin">
      <td>LinkedIn</td>
      <td><i class="fa fa-linkedin fa-lg"></i></td>
      <td><i class="fa fa-linkedin-square fa-lg"></i></td>
      <td><span class="fa-stack fa-lg">
        <i class="fa fa-square fa-stack-2x"></i>
        <i class="fa fa-linkedin fa-stack-1x fa-inverse"></i>
      </span></td>
      <td><span class="fa-stack fa-lg">
        <i class="fa fa-square-o fa-stack-2x"></i>
        <i class="fa fa-linkedin fa-stack-1x"></i>
      </span></td>
      <td><span class="fa-stack fa-lg">
        <i class="fa fa-circle fa-stack-2x"></i>
        <i class="fa fa-linkedin fa-stack-1x fa-inverse"></i>
      </span></td>
      <td><span class="fa-stack fa-lg">
        <i class="fa fa-circle-o fa-stack-2x"></i>
        <i class="fa fa-linkedin fa-stack-1x"></i>
      </span></td>
      <td><span class="fa-stack fa-lg">
        <i class="fa fa-circle-thin fa-stack-2x"></i>
        <i class="fa fa-linkedin fa-stack-1x"></i>
      </span></td>
      <td><span class="fa-stack fa-lg">
        <i class="fa fa-comment fa-stack-2x"></i>
        <i class="fa fa-linkedin fa-stack-1x fa-inverse"></i>
      </span></td>
      <td><span class="fa-stack fa-lg">
        <i class="fa fa-comment-o fa-stack-2x"></i>
        <i class="fa fa-linkedin fa-stack-1x"></i>
      </span></td>
    </tr>
  </tbody>
</table>

---

#### **Icon Links**

I'll use the `fa-<brand>-square` series of brand icons for these examples as they're the most authentic.

##### Twitter:
<a class="twitter" href="https://twitter.com/intent/tweet?text={{page.title}}:&url={{site.url}}{{page.url}}&via={{site.twitter_username}}&related={{site.twitter_related}}&hashtags={% for tag in page.tags %}{{tag}},{% endfor %}" rel="nofollow" target="_blank"><i class="fa fa-twitter-square fa-fw fa-3x"></i></a>

{% highlight html %}
{% raw %}
<a class="twitter" href="https://twitter.com/intent/tweet?text={{page.title}}:&url={{site.url}}{{page.url}}&via={{site.twitter_username}}&related={{site.twitter_related}}&hashtags={% for tag in page.tags %}{{tag}},{% endfor %}" rel="nofollow" target="_blank"><i class="fa fa-twitter-square fa-fw fa-3x"></i></a>
{% endraw %}
{% endhighlight %}


##### Facebook:
<a class="facebook" href="https://facebook.com/sharer.php?u={{ site.url }}{{ page.url }}" rel="nofollow" target="_blank"><i class="fa fa-facebook-square fa-fw fa-3x"></i></a>

{% highlight html %}
{% raw %}
<a class="facebook" href="https://facebook.com/sharer.php?u={{ site.url }}{{ page.url }}" rel="nofollow" target="_blank"><i class="fa fa-facebook-square fa-fw fa-3x"></i></a>
{% endraw %}
{% endhighlight %}


##### Google+:
<a class="google-plus" href="https://plus.google.com/share?url={{ site.url }}{{ page.url }}" rel="nofollow" target="_blank"><i class="fa fa-google-plus-square fa-fw fa-3x"></i></a>

{% highlight html %}
{% raw %}
<a class="google-plus" href="https://plus.google.com/share?url={{ site.url }}{{ page.url }}" rel="nofollow" target="_blank"><i class="fa fa-google-plus-square fa-fw fa-3x"></i></a>
{% endraw %}
{% endhighlight %}

##### LinkedIn:
<a class="linkedin" href="http://www.linkedin.com/shareArticle?mini=true&url={{site.url}}{{page.url}}&title={{page.title}}&source={{site.title}}" rel="nofollow" target="_blank"><i class="fa fa-linkedin-square fa-fw fa-3x"></i></a>


{% highlight html %}
{% raw %}
<a class="linkedin" href="http://www.linkedin.com/shareArticle?mini=true&url={{site.url}}{{page.url}}&title={{page.title}}&summary={{page.excerpt|strip_html}}&source={{site.title}}" rel="nofollow" target="_blank"><i class="fa fa-linkedin-square fa-fw fa-3x"></i></a>
{% endraw %}
{% endhighlight %}

---

#### **Buttons**

##### Twitter:
<p><a class="btn btn-default twitter" href="https://twitter.com/intent/tweet?text={{page.title}}:&url={{site.url}}{{page.url}}&via={{site.twitter_username}}&related={{site.twitter_related}}&hashtags={% for tag in page.tags %}{{tag}},{% endfor %}" rel="nofollow" target="_blank"><i class="fa fa-twitter fa-fw fa-lg"></i> Twitter</a></p>

{% highlight html %}
{% raw %}
<p><a class="btn btn-default twitter" href="https://twitter.com/intent/tweet?text={{page.title}}:&url={{site.url}}{{page.url}}&via={{site.twitter_username}}&related={{site.twitter_related}}&hashtags={% for tag in page.tags %}{{tag}},{% endfor %}" rel="nofollow" target="_blank"><i class="fa fa-twitter fa-fw fa-lg"></i> Twitter</a></p>
{% endraw %}
{% endhighlight %}


##### Facebook:
<p><a class="btn btn-default facebook" href="https://facebook.com/sharer.php?u={{ site.url }}{{ page.url }}" rel="nofollow" target="_blank"><i class="fa fa-facebook fa-fw fa-lg"></i> Facebook</a></p>

{% highlight html %}
{% raw %}
<p><a class="btn btn-default facebook" href="https://facebook.com/sharer.php?u={{ site.url }}{{ page.url }}" rel="nofollow" target="_blank"><i class="fa fa-facebook fa-fw fa-lg"></i> Facebook</a></p>
{% endraw %}
{% endhighlight %}


##### Google+:
<p><a class="btn btn-default google-plus" href="https://plus.google.com/share?url={{ site.url }}{{ page.url }}" rel="nofollow" target="_blank"><i class="fa fa-google-plus fa-fw fa-lg"></i> Google+</a></p>

{% highlight html %}
{% raw %}
<p><a class="btn btn-default google-plus" href="https://plus.google.com/share?url={{ site.url }}{{ page.url }}" rel="nofollow" target="_blank"><i class="fa fa-google-plus fa-fw fa-lg"></i> Google+</a></p>
{% endraw %}
{% endhighlight %}

##### LinkedIn:
<p><a class="btn btn-default linkedin" href="http://www.linkedin.com/shareArticle?mini=true&url={{site.url}}{{page.url}}&title={{page.title}}&source={{site.title}}" rel="nofollow" target="_blank"><i class="fa fa-linkedin fa-fw fa-lg"></i> LinkedIn</a></p>

{% highlight html %}
{% raw %}
<p><a class="btn btn-default linkedin" href="http://www.linkedin.com/shareArticle?mini=true&url={{site.url}}{{page.url}}&title={{page.title}}&source={{site.title}}" rel="nofollow" target="_blank"><i class="fa fa-linkedin fa-fw fa-lg"></i> LinkedIn</a></p>
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
          <a class="twitter" href="https://twitter.com/intent/tweet?text={{page.title}}:&url={{site.url}}{{page.url}}&via={{site.twitter_username}}&related={{site.twitter_related}}&hashtags={% for tag in page.tags %}{{tag}},{% endfor %}"
          rel="nofollow" target="_blank">
          <i class="fa fa-twitter-square fa-fw fa-3x"></i></a>
          <a class="facebook" href="https://facebook.com/sharer.php?u={{ site.url }}{{ page.url }}"
          rel="nofollow" target="_blank">
          <i class="fa fa-facebook-square fa-fw fa-3x"></i></a>
          <a class="google-plus" href="https://plus.google.com/share?url={{ site.url }}{{ page.url }}"
          rel="nofollow" target="_blank">
          <i class="fa fa-google-plus-square fa-fw fa-3x"></i></a>
          <a class="linkedin" href="http://www.linkedin.com/shareArticle?mini=true&url={{site.url}}{{page.url}}&title={{page.title}}&source={{site.title}}" rel="nofollow" target="_blank"><i class="fa fa-linkedin-square fa-fw fa-3x"></i></a>
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
          <a class="twitter" href="https://twitter.com/intent/tweet?text={{page.title}}:&url={{site.url}}{{page.url}}&via={{site.twitter_username}}&related={{site.twitter_related}}&hashtags={% for tag in page.tags %}{{tag}},{% endfor %}"
          rel="nofollow" target="_blank">
          <i class="fa fa-twitter-square fa-fw fa-3x"></i></a>
          <a class="facebook" href="https://facebook.com/sharer.php?u={{ site.url }}{{ page.url }}"
          rel="nofollow" target="_blank">
          <i class="fa fa-facebook-square fa-fw fa-3x"></i></a>
          <a class="google-plus" href="https://plus.google.com/share?url={{ site.url }}{{ page.url }}"
          rel="nofollow" target="_blank">
          <i class="fa fa-google-plus-square fa-fw fa-3x"></i></a>
          <a class="linkedin" href="http://www.linkedin.com/shareArticle?mini=true&url={{site.url}}{{page.url}}&title={{page.title}}&source={{site.title}}" rel="nofollow" target="_blank"><i class="fa fa-linkedin-square fa-fw fa-3x"></i></a>
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
          <p><a class="btn btn-default btn-block twitter" href="https://twitter.com/intent/tweet?text={{page.title}}:&url={{site.url}}{{page.url}}&via={{site.twitter_username}}&related={{site.twitter_related}}&hashtags={% for tag in page.tags %}{{tag}},{% endfor %}"
          rel="nofollow" target="_blank">
          <i class="fa fa-twitter fa-fw fa-lg"></i> Twitter</a></p>
          <p><a class="btn btn-default btn-block facebook" href="https://facebook.com/sharer.php?u={{ site.url }}{{ page.url }}"
          rel="nofollow" target="_blank">
          <i class="fa fa-facebook fa-fw fa-lg"></i> Facebook</a></p>
          <p><a class="btn btn-default btn-block google-plus" href="https://plus.google.com/share?url={{ site.url }}{{ page.url }}"
          rel="nofollow" target="_blank">
          <i class="fa fa-google-plus fa-fw fa-lg"></i> Google+</a></p>
          <p><a class="btn btn-default btn-block linkedin" href="http://www.linkedin.com/shareArticle?mini=true&url={{site.url}}{{page.url}}&title={{page.title}}&source={{site.title}}" rel="nofollow" target="_blank"><i class="fa fa-linkedin fa-fw fa-lg"></i> LinkedIn</a></p>
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
          <p><a class="btn btn-default btn-block twitter" href="https://twitter.com/intent/tweet?text={{page.title}}:&url={{site.url}}{{page.url}}&via={{site.twitter_username}}&related={{site.twitter_related}}&hashtags={% for tag in page.tags %}{{tag}},{% endfor %}"
          rel="nofollow" target="_blank">
          <i class="fa fa-twitter fa-fw fa-lg"></i> Twitter</a></p>
          <p><a class="btn btn-default btn-block facebook" href="https://facebook.com/sharer.php?u={{ site.url }}{{ page.url }}"
          rel="nofollow" target="_blank">
          <i class="fa fa-facebook fa-fw fa-lg"></i> Facebook</a></p>
          <p><a class="btn btn-default btn-block google-plus" href="https://plus.google.com/share?url={{ site.url }}{{ page.url }}"
          rel="nofollow" target="_blank">
          <i class="fa fa-google-plus fa-fw fa-lg"></i> Google+</a></p>
          <p><a class="btn btn-default btn-block linkedin" href="http://www.linkedin.com/shareArticle?mini=true&url={{site.url}}{{page.url}}&title={{page.title}}&source={{site.title}}" rel="nofollow" target="_blank"><i class="fa fa-linkedin fa-fw fa-lg"></i> LinkedIn</a></p>
        </div>
      </div>
    </div>
  </div>
</div>
{% endraw %}
{% endhighlight %}

##### List Panel:

<div class="row">
  <div class="col-xs-12 col-sm-4">
    <div class="panel panel-default">
      <div class="list-group">
        <div class="list-group-item">
          <h5 class="list-group-item-heading"><i class="fa fa-share-alt fa-fw"></i> Share</h5>
        </div>
        <a class="list-group-item" href="https://twitter.com/intent/tweet?text={{page.title}}:&url={{site.url}}{{page.url}}&via={{site.twitter_username}}&related={{site.twitter_related}}&hashtags={% for tag in page.tags %}{{tag}},{% endfor %}"
          rel="nofollow" target="_blank">
          <i class="fa fa-twitter fa-fw fa-lg twitter"></i> Twitter</a></p>
        </a>
        <a class="list-group-item" href="https://facebook.com/sharer.php?u={{ site.url }}{{ page.url }}"
          rel="nofollow" target="_blank">
          <i class="fa fa-facebook fa-fw fa-lg facebook"></i> Facebook</a></p>
        </a>
        <a class="list-group-item" href="https://plus.google.com/share?url={{ site.url }}{{ page.url }}"
          rel="nofollow" target="_blank">
          <i class="fa fa-google-plus fa-fw fa-lg google-plus"></i> Google+</a></p>
        </a>
        <a class="list-group-item" href="http://www.linkedin.com/shareArticle?mini=true&url={{site.url}}{{page.url}}&title={{page.title}}&source={{site.title}}" rel="nofollow" target="_blank"><i class="fa fa-linkedin fa-fw fa-lg linkedin"></i> LinkedIn</a></p>
        </a >
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
        <a class="list-group-item" href="https://twitter.com/intent/tweet?text={{page.title}}:&url={{site.url}}{{page.url}}&via={{site.twitter_username}}&related={{site.twitter_related}}&hashtags={% for tag in page.tags %}{{tag}},{% endfor %}"
          rel="nofollow" target="_blank">
          <i class="fa fa-twitter fa-fw fa-lg twitter"></i> Twitter</a></p>
        </a>
        <a class="list-group-item" href="https://facebook.com/sharer.php?u={{ site.url }}{{ page.url }}"
          rel="nofollow" target="_blank">
          <i class="fa fa-facebook fa-fw fa-lg facebook"></i> Facebook</a></p>
        </a>
        <a class="list-group-item" href="https://plus.google.com/share?url={{ site.url }}{{ page.url }}"
          rel="nofollow" target="_blank">
          <i class="fa fa-google-plus fa-fw fa-lg google-plus"></i> Google+</a></p>
        </a>
        <a class="list-group-item" href="http://www.linkedin.com/shareArticle?mini=true&url={{site.url}}{{page.url}}&title={{page.title}}&source={{site.title}}" rel="nofollow" target="_blank"><i class="fa fa-linkedin fa-fw fa-lg linkedin"></i> LinkedIn</a></p>
        </a >
      </div>
    </div>
  </div>
</div>
{% endraw %}
{% endhighlight %}
