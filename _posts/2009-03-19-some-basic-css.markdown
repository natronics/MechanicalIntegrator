---
layout: post
title: Some Basic CSS
categories: [Code]
tags: [blogs, coding, css, html, pdxwp]
---

Anyone who at some point has had to build or edit a web page has
probably at least heard of CSS. What is it exactly? It's a markup
language that is used to define how to display HTML elements on
a web page. It has become the dominate way to control the colors
fonts and layout of a web page.

Why does everyone like CSS? It lets you separate the presentation
part of a web page (color, typography, etc.) from the content. That
way if you want to re-style a site you only have to change the
CSS—in one place—and not the whole site.

<!--more-->

But I'm sure you already knew all that. How does one go about actually
using it? First you have to understand just a little bit about the
basic structure of the language.


### Basics

CSS lets you use something called _selectors_ to _select_ pieces of the
HTML and style them. For instance if you have a page with one `div`
and inside that one `p`. In the CSS you can add style to just the `div`
and or just the `p`. You do this by simply starting a line of CSS with
the name of the element, let's say `p`, then all of the style for that
selector goes in between a set of curly braces.


**Ex. 1, Hello World**

{% highlight css %}
p {
    color: red;
}
{% endhighlight %}


Now everything on your page in a `p` will have have a red text color. But
you can select with a far more granular level of control than just element
type. Remember that the code above will effect _every_ `p` tag on the entire
page! Instead we want to use logical names and some hierarchy rules.

Luckily this is pretty easy to do. Just about every element in HTML has
optional attributes called `id` and `class`. If you set give an element an
id then you can refer to that id in the CSS and control just that one element.
Same with class. The difference between class and id is that according to
the HTML spec you are only allowed one element with a particular id.
Conversely you can reuse a class on as many elements as you want.

To handle hierarchy you just write out the selectors in the order that
they appear on the page.


**Ex. 2, Advanced Selectors**

{% highlight css %}
/*Style for every p on the page*/
p {
    color: red;
}
 
/*Style for an element with the id "foo"*/
#foo {
    color: blue;
}
 
/*Style for every element on the page 
with the class "bar"*/
.bar {
    color: green;
}
 
/*Style for every p tag inside a div tag*/
div p {
    color: black;
}
 
/*Getting fancy now, style every 
p tag inside an element with 
class "bar" that is in the 
element with an id "foo"*/
#foo .bar p {
    color: white;
}
{% endhighlight %}


So what happens when an element is in more than one selector?
For instance in the example above how does a p tag that satisfies
the last selector get know to be white rather than red (from the
first selector)? The answer comes from the 'cascading' part of
cascading style sheets. If you have conflicting selectors, but
with different properties in them, then the element gets style from
both. If both selectors have the _same_ property, but with different
values then the _most specific_ one wins. What do I mean?

**Ex. 3, Inheritance**

{% highlight css %}
p {
    background: #f4c;
    color: #000;
}
 
div p {
    color: #fff;
}
 
#foo {
    color: #ccc;
}
{% endhighlight %}

In this case all `p`'s get a background color of `#FF44CC` and a
text color of `#000000`. But, if there is a p inside a div,
this is more specific than just any p. It still retains the
background color but gets the text color `#FFFFFF`. And if a p
has an id of "foo" then that is even more specific and so again
it keeps the background color but gets the ext color `#CCCCCC`.

This actually keeps getting more and more complicated with crazy
things like [pseudo-classes](http://www.w3schools.com/CSS/css_pseudo_classes.asp)
and other advanced ways to get to elements.
But the above is enough to get started actually changing things.

Now that you know how to get to a element on a page, what can you do
with it? This is where the style part of cascading style sheets comes
in. CSS has a number of properties that can be set on any object. In
the examples I've already hinted at two of them, **background** and **color**.
There are many more. In fact rather than list them here check out
these handy dandy reference sites:

 - [CSS Reference from Stylegala](http://www.stylegala.com/features/css-reference/index.html)
 - [CSS Reference from w3schools](http://www.w3schools.com/css/css_reference.asp)
 - [CSS Reference from xhtml.com](http://xhtml.com/en/css/reference/)
 - [O'Reily's pocket CSS Guide (a book, if you're into that sort of thing)](http://oreilly.com/catalog/9780596515058/)

I highly encourage reading over these once or twice to get an idea of
what you can do, but don't think you have to memorize it all! Even
processionals occasionally cheat and look at references. One note about
colors, if you're not already familiar with the hexadecimal notation for
colors and were wondering what all that #fe4563; mess is then
[read this](http://vlaurie.com/computers2/Articles/hexed.htm).


### Getting down to business

Instead of all this theory it's best if we just look at some examples
and see how to accomplish some common things.

**Ex. 4, Add some padding around an element**

{% highlight css %}
p {
    padding: 25px;          /*25 pixel padding around the whole object. */
    padding-left: 50px;     /*50 pixel padding on the left of the object. */
    padding: 10px 14px 0 3px;  /*Shorthand: first value is padding on top, then right, bottom then left. */
}
 
p {
    margin: 34px;       /*Works  exactly the same as padding, but things like background color don't apply*/
}
{% endhighlight %}


The best way to space out items on a page is to have rules for
margin and padding set for everything. The difference between the two
is that margin is the spacing _outside_ of the element and padding is the
spacing on the _inside_.


**Ex. 5, Make a Border**

{% highlight css %}
#one {
    border: 1px solid #fc2;
}
 
#two {
    border-right: 3px dashed #4fc;
}
{% endhighlight %}


Borders are super easy.


**Ex. 6, Typography**

{% highlight css %}
p {
    font-family: Georgia, "Times New Roman", Times, serif;
    font-size: 1.3em;
    line-height: 1.5em;
}
{% endhighlight %}

Typography is a tricky thing on the web. There is no guarantee that you're
audience's computer has the same font's installed that you do. When you
give an element a font-family you should always give it a failover or two.
At the very least end it with either 'serif' or 'sans-serif'. Just about every
browser understands that. What the browser will do in this example is try to
use the Georgia typeface and if that is not installed it will use Times New
Roman, and if that is not installed it will use Times, and if none of those are
installed then it will use the default serif font for the users computer.

Actually when it comes to typography on the web there are a lot of tools
out there that will write CSS for you. Two good ones to look at are
[Typetester](http://www.typetester.org/) and
[Typeograph](http://lamb.cc/typograph/). These tools with let you choose
what you want the type to look like and the give you the CSS to accomplish
that goal. Also Portland's own
[@brampitoyo](http://twitter.com/brampitoyo) gave a talk a while back
that was a
[great introduction to typesetting for blogs](http://tr.im/readbetter).
Some of the slides have CSS examples on them.


**Ex. 7, Hide Something**

{% highlight css %}
p {
    display: none;
}
{% endhighlight %}

This will effectively remove the element from the page. It's won't show and
other elements on the page will try and take it's place. If you just want it
to be hidden but not totally gone use 'visibility: hidden;' instead.


**Ex. 8, Image as Backgrounds**

{% highlight css %}
p {
    background: #fff url('image/image.png') top left no-repeat;
}
{% endhighlight %}


Instead of just a color you can include an image as the background of an
element. You can control where the image is positioned in the element
(`top left`) and whether or not it repeats (`no-repeat`, `repeat-x`,
`repeat-y` or `repeat-xy`).

Again all this detail cab be found in reference sites and books.


### Practical Advice

It took me an awfully long time to get to this point, but now that we are all
on the same page, here is my advice for actually doing something with a design
in the real world.

When you have an existing page that is mostly laid out, say a
[WordPress theme](http://wordpress.org/extend/themes/),
then you don't need to be able to start from scratch and build up all kinds of
fancy rules for every type of thing on your page. But you might want to adjust
it a little. Maybe you want to change the font or a background color. This is
actually very easy these days. There is a really fine tool that comes as a
plugin for Firefox called [Firebug](https://addons.mozilla.org/en-US/firefox/addon/1843).
If you don't have Firefox or some derivative
of it, you should just take this opportunity to download it. Then go to the
firebug site and install the plugin. What firebug does is allow you to see in real
time the style of every element on the page. You can even change it on the page
and see what effect it will have in real time. It also has a JavaScript debugger
and several other advanced features.

Specifically once you are on a page then click the Firebug icon in the lower
right-hand corder of the browser. Then you can click the 'inspect' button and
whatever you click on in the page it will show you the HTML on the left and
the CSS on the right that apply to that element.

<div class="gallery row">
 <div class="col-sm-8 col-md-5">
  <div class="thumbnail">
   <img alt="Firebug icon" src="/resources/photos/firebug_icon.png" class="responsive">
   <div class="caption">
    <p>The Firebug icon</p>
   </div>
  </div>
 </div>
</div>

This will let you see what CSS has already been applied and which parts
are overridden by which other parts. Any line of CSS in the right-hand window
has a cross out icon when you hover over it. Clicking this will allow you to
temporarily hide that line of CSS and see what happens to the page. I use this
all the time to figure out what exactly the CSS is doing. A word of caution, it
might look like a line does nothing, but that probably means that it is a fix
for another browser! Also if you double click at the bottom of a set of CSS you
can add a new line and type in your custom CSS and watch it update in real time!
Note that Firebug does not actually update anything permanently. If you are
working on your site you will still need to update the CSS on the server.

Firebug and WordPress' built in theme editor make is super easy to update you're
blog's look and feel. All you have to do is go your blog and open Firebug and use
the inspect button to click on the thing you want to change. Look at the CSS it
already has. The selector at the top is the most specific and you can see the other
selectors that below it. It's safest to just change the top most selector. You can
test out changing a value by double clicking it or add a new one by double clicking
at the bottom. Once you have the look you are going for navigate to your dashboard
and find the theme editor page. Choose "style.css" or whatever appropriate file
(it will also say in Firebug) to edit it then find that same bit of CSS you edited
in Firebug and write it in and save your changes. Go back to your site and hit refresh.
You might have to hold down shift and refresh in case your browser cached the old
CSS. Just repeat those steps until your satisfied.

<div class="gallery row">
 <div class="col-sm-8 col-md-5">
  <a class="thumbnail" href="/resources/photos/firebug.png">
   <img alt="Firebug running" src="/resources/photos/firebug_small.png" class="responsive">
   <div class="caption">
    <p>Firebug running</p>
   </div>
  </a>
 </div>
</div>

There are some even easier ways to do some common things like change all the colors
in a CSS file.
[CSS Color Editor](http://css-color-replace.orca-multimedia.de/) takes a file
(just copy and past it from WordPress
theme editor to notepad) and shows you every color used in that CSS file. Then you
tell it what colors you want to replace and it gives you the new CSS file with the
new colors. Here is a list of a several more tools that are fun to play with from
[CSS Orgy](http://cssorgy.com/10-great-tools-for-working-with-html-css-750).


### Pitfalls

Watch out! Not every browser handles the same CSS the same way. Unfortunately
there isn't much you can do about this except practice and test your page in every
browser you can think of. If you don't actually have all the browsers ever installed
you can go to
[BrowserShots](http://browsershots.org/) and have them render it for you and they give you
screenshots of every combination of browser/OS. It's free the first time ;)

In general one thing to stay away from is depending on the border width to space
things, always use margin or padding. Most of the good CSS references will tell
you what property is supported in what browser.


### You Can do It

It there is one thing you should know it's that you can do it! I figured all this
out myself a few years ago in my free time because I was bored and I thought it
was cool. You can do it too. The best way to learn is to just get in there and
try stuff. Write a simple little HTML page and then play around with the style.
Go crazy with it, break it, then learn what does and doesn't work. Also look out
for inspiration. There is nothing wrong with looking at other sites that do
something well and learning from them. Using firebug you can peak under the hood
of every site out there! I always tell CSS newcomers to check out
[CSS Zen Garden](http://www.csszengarden.com/).
The site consists on just one page, the home page. But you can use the links on the
side to change the look of the site completely. Hundreds of graphic artists have
contributed designs over the years. What's amazing is that all of the different
designs rely on the exact same HTML! The only thing they changed is the CSS. If
you're bored one day just search for
"[css gallery](http://www.google.com/search?q=css+gallery)" and see what comes up.

Good luck!
