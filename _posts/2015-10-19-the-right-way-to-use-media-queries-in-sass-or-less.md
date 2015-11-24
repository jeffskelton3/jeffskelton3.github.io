---
layout: post
title:  "The Right Way To Use Media Queries In Sass or LESS"
date:   2015-10-19 17:29:25
categories: [programming]
tags: [css, less, sass, responsive, tutorials]
---
The web has changed a lot since I started out. With so many screen sizes possible the old approach of using a single layout has largely fallen out of favor. Today a website typically has at least three layouts: phone, tablet, and desktop. In reality its usually a lot more complicated but lets just stick to those three for now. This tutorial hopes to show you a sane way to manage that complexity.

### Media Queries To The Rescue (Right?)
The widespread browser support for media queries in CSS has saved us from the dark days of using ugly JavaScript hacks to detect the size of our viewport. These days using different CSS rules for different screen sizes is a fairly straight forward affair. Just wrap the rules you mean to use in a media query and be done with it:

{% highlight Sass %}

p{
    color: black;
}

@media(min-width:480px) and (max-width: 768px){
    /*rules will only apply when the viewport is between 300px and 700px*/
    p{
        color: purple;
    }
}

{% endhighlight %}

Ok so we're done right? We can go home? Well not exactly. While media queries are incredibly convenient, they can add an _insane_ amount of complexity and noise to a project. An organizational approach I see fairly often is to use a separate file for each size (typically a "mobile" and "tablet" file). While this seems like a good idea, in reality it's a *terrible* approach. You've just tripled the amount of code you've written. Worse, you now have to remember to make changes in 3 different places which violates [DRY](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself) principles.

### A Better Way
Ok so separating your markup out by viewport doesn't work. So how to best manage this mountain of complexity you've just heaped upon yourself? The technique that I've employed with the most success is to use my media queries _by component_ via a CSS preprocessor such as [Sass](http://sass-lang.com/) or [LESS](http://lesscss.org/). That is to apply them directly inside the rule like so:

{% highlight Sass %}

p{
    color: black;
    @media(min-width:480px) and (max-width: 768px){
        /*rules will only apply when the viewport is between 480px and 768px*/
        p{
            color: purple;
        }
    }
}

{% endhighlight %}

Right away we see that things are much easier to keep track of. All style rules relating to a given selector are right there and easy to follow along with. We can improve this even more by leveraging some variables to manange our viewport breakpoints.

{% highlight Sass %}

$xs-viewport : 480px; //phone sized screens
$sm-viewport : 768px; //tablet sized screens
$md-viewport : 992px; //laptop sized screens
$lg-viewport : 1200px; //extra wide screens

p{
    color: black;
    @media(min-width:$xs-viewport) and (max-width: $sm-viewport){
        /*rules will only apply when the viewport is between 300px and 700px*/
        p{
            color: purple;
        }
    }
}

{% endhighlight %}

Using variables to define our screen sizes means that maintaining and more importantly _remembering_ our layouts breakpoints becomes centralized and trivial to maintain. If we suddenly need to change a break point to accommodate a screen resolution we had not anticipated, we only have to do it in one place. If nothing else take this to heart. It will save you hours of your life!

Now that we are bundling our style rules by component and properly leveraging variables to manange our breakpoints there is only one more thing: Order of precedence. The term "mobile first" is bandied around a lot these days but what does it mean? While there are a lot of different ways to answer that question, in our case it means that we should be defining our style rules by *the smallest viewport first and then overriding as we move outward to the larger ones*. This is a super important concept to grasp as it brings together all of the techniques described above and leverages them for maximum impact. Lets apply this technique to our example:

{% highlight Sass %}

$xs-viewport : 480px; //phone sized screens
$sm-viewport : 768px; //tablet sized screens
$md-viewport : 992px; //laptop sized screens
$lg-viewport : 1200px; //extra wide screens

p{
    //default style rules. Defined for the smallest viewport and then override as needed for larger
    color: black;
    font-size: 14px;

    @media(min-width:$xs-viewport){
        //rules that only apply when the viewport is larger than 480px
        p{
            color: purple;
            font-size: 16px;
        }
    }


    @media(min-width:$sm-viewport){
        //rules that only apply when the viewport is larger than 768px
        p{
            margin: 20px 0;
            font-size: 16px;
        }
    }


    @media(min-width:$md-viewport){
        //rules that only apply when the viewport is larger than 992px
        p{
            font-size: 18px;
        }
    }
}


{% endhighlight %}

Notice how we don't add a `max-width` property to our media queries. With this approach there is no need and it adds unnecessary complexity since our goal is to override our rules as we expand out. There are exceptions to every rule of course but by and large there is no need if employed correctly. The above rule keeps all the rules of its smaller viewports and only overrides those that need to be in the larger. The essentially _cascade_ into one another quite nice which is exactly how native CSS works.

So there you have it. I've used this approach on some very large projects. It has been battle tested and works wonderfully. If you disagree or have an improvement feel free to [contact me](mailto:jeff@jeffskelton.net) and let me know. I'm always looking for a better way.