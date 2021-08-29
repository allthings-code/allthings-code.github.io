---
layout: post
title:  "Strange Case of Dr. Jekyll and Mr. Hyde"
date:   2021-08-16 23:32:43 -0700
published: false
categories: jekyll ruby github static web liquid
---

"Life is not a matter of holding good cards, but of playing a poor hand well." - Robert Louis Stevenson

# Introduction
If you're thinking "Wait a minute, this is a programming blog and not a gothic Scottish novel about a shapeshifting doctor?! What gives?" then stop right there!
Jekyll (the tool, not the doctor) is quite similar to its' namesake - but rather than turn into a serial murderer - Jekyll turns generic markdown files into a static website. It allows you to serve user content quickly and easily.

# Background
Written in [Ruby][https://www.ruby-lang.org/en/documentation/] by [Tom Preston-Werner][https://en.wikipedia.org/wiki/Tom_Preston-Werner] in the year 2008, Jekyll was a pioneer in the space of [static web pages][https://en.wikipedia.org/wiki/Static_web_page]. As opposed to their dynamic cousins, static web pages are more secure, easier to maintain, and a whole lot less complicated. They present the same content, usually [markdown]https://www.markdownguide.org/getting-started/ files, to every user in exactly the same way. No calls to complicated middleware and backends. Static sites are the no fuss, no muss of the front end worl. Tom Preston-Werner went on later in his career to cofound [Github][https://github.com/] where Jekyll was slated as the engine behind [Github Pages][https://pages.github].com/. Now Jekyll is the most widely adopted static web page generator.

# Jekyll Project Layout
So how exactly does Jekyll work? It's quite simple really. First, you'll need to understand the layout of a jekyll project. (Since Jekyll 3.2, this layout has had a bit of a rework. The main premise still applies.)

INSERT PICTURE OF LAYOUT HERE

While every file and directory shown is important, you really need to understand _config.yml, _posts, _layouts, and _site.
_config.yml hosts site wide settings that you might need to reference multiple times. Something like your site title or contact email.
_posts as the name implies, hosts your sites content. Since Jekyll caters to the blogging scene, this content is usually in the form of blog post markdown files.
_layouts hosts the html design of common pages across your Jekyll project. These designs form a skeleton around the content in _posts.
Finally, _site will host the successfully generated build of your static Jekyll project. This is where Jekyll stores its' output and what is actually shown to the world as a website.

# Jekyll's Secret Serum
Now that we have a base understanding of how Jekyll projects are structured, we can discuss how Jekyll actually works. First step in turning your static content into a real website is composing all files within the _posts directory into post objects. Jekyll then composes all files withn the _layouts directory as layout objects. Thing of this as a preperation stage. Jekyll is just preparing the site content into usable objects.

Next,

Then, Jekyll creates one giant ruby object by combining these composed posts/layouts with site metadata (dates, titles, links, etc).

Jekyll then uses a language called [Liquid][https://shopify.github.io/liquid/] to liquify all posts and layouts.

Finally, these liquified templates and posts are rendered.

# Terms
Static Web Pages
Liquid
Liquify
Ruby
Jekyll
directory

# Appendix
http://jekyllbootstrap.com/lessons/jekyll-introduction.html#:~:text=The%20following%20is%20an%20outline%20of%20how%20that%27s,and%20templates.%20...%204%20Jekyll%20generates%20output.%20

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
