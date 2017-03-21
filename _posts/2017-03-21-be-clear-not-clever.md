---
layout: hpstr/post
title: "Be Clear, Not Clever"
date: 2017-03-21T11:24:47-07:00
---

> "Write code that is easy to delete, not easy to extend." - [Programming Is Terrible](http://programmingisterrible.com/post/139222674273/write-code-that-is-easy-to-delete-not-easy-to)

One of the most common pitfalls I see in beginner to intermediate level programmers is a desire to optimize their code for extensibility too early in the process. While this sounds like a good idea, often they try to solve for problems that are not explicitly stated in the requirements. In other words, they try to write code that can adapt to _any_ changes and not just the ones they know about. This is a mistake. 

> "Premature optimization is the root of all evil" - [Donald Knuth](https://en.wikiquote.org/wiki/Donald_Knuth)

A more experienced developer follows the philosophy of **make it work, make it good, make it fast**. 

### 1) Make it work
First, do whatever needs to be done to make the feature work. Write tests which state the expected behavior and verify that they fail. Begin writing your code. Ignore code quality to a reasonable extent and duplication is ok for the time being. The only focus here is getting tests to pass.

### 2) Make it good
The process of building out a new feature exposes the areas that need to be optimized. This is the time to review what has been built and begin refactoring. Duplication should be eliminated. Variables and function names should be carefully thought out. Code should be modularized and organized into logical sections. All tests should continue to pass.

### 3) Make it fast
Identify any obvious performance bottlenecks. Revisit this step as the new feature is used. The areas for optimization will become obvious. As stated before, avoid making assumptions or writing overly torturous logic to solve for problems you don't yet have. 

## Common trouble spots

> "You wanted a banana but what you got was a gorilla holding the banana and the entire jungle." - [Joe Armstrong, creator of Erlang](https://www.amazon.com/gp/product/1430219483?ie=UTF8&tag=theende-20&linkCode=xm2&camp=1789&creativeASIN=1430219483)

I am not a purist. I believe that whatever gets the job done with the least amount of complexity, is the right approach. It's trendy today to bash on Object Oriented Programming (OOP) but I feel that to be overly dogmatic. OOP has a lot of powerful comcepts and an inexperienced programmer can easily abuse them by trying do too much too early. 

### Abuse of inheritance

In my opinion abuse of inheritance is the biggest culprit. Inheritance, when done right can be a powerful concept. When done wrong it can create a massive headache as a codebase increases in size and complexity. In Steve McConnel's excellent book [Code Complete 2]({{ "/2017/03/12/recommended-reading.html" | prepend: site.baseurl }}), he recommends limiting levels of inheritance to no more than 3 levels. I would argue that that number should be 2 unless there is a very good reason. More importantly I feel that using inheritance can wait until much later in the process when its much more clear where it will be useful. 

<iframe width="560" height="315" src="https://www.youtube.com/embed/QM1iUe6IofM" frameborder="0" allowfullscreen></iframe>

<small>*I don't agree that OOP is bad. However, I do think that the author brings up some good points.</small>

 Functional programming teaches us some valuable techniques. It teaches us to write our code as a series of small, composable blocks. We chain these blocks together and build complex pipelines of logic. Each block has a single responsibility. This approach allows us to easily delete or change that block of logic with minimal danger of affecting the entire application. A good deal of the time I find this to be the best way to approach things. **Whenever possible, write code that is explicit in its dependencies.**

This is one of the reasons I love working with a language like Elixir. It allows for elegant code blocks like this:

{% highlight ruby %}    
doTheThing
  |> doTheNextThing
  |> doTheFinalThing
{% endhighlight %}

In JavaScript we can accomplish something similar with promise chaining:

{% highlight javascript %}
doTheThing()
  .then(doTheNextThing)
  .then(doTheFinalThing)
{% endhighlight %}

This is powerful because if I wanted to add a new piece of logic to my code, I can simply add it to the chain:

{% highlight javascript %}
doTheThing()
  .then(doTheNextThing)
  .then(doAThirdThing)
  .then(doTheFinalThing)
{% endhighlight %}

### Abuse of novel language/framework features

This doesn't just affect traditional code either. Take this Sass example I just saw at a frontend conference recently.

{% highlight javascript %}
.primary-rail{
  @extend .pull-left, .col-md-6, .small;
}
{% endhighlight %}

The speaker presents this as a clever way to encapsulate all his CSS classes into one large "God" class. While it's neat that you _can_ do this. It's a terrible idea in practice. What happens for example if he encounters a case where the column needs to be a different size? He can't change it here without affecting everything else. What about cases where he only wants some but not all of those classes? Whats worse, he has abstracted away some relatively well known bootstrap classes in favor of his own domain specific language (DSL). Now any new developer that works on his code needs to root about to find out what that class does. As the application ages, it will become increasingly unclear what the ramifications of changing that class would mean to the application at large. Since that styling likely touches a lot of areas in the application, no one will dare change it for fear that it will have largely unforseen consequences. It is for this reason that I strongly recommend a more modular approach. The time saved by encapsulating these classes behind a DSL is lost in the mental overhead required to understand it and the long term maintenance overhead it presents.   

It's a fact that the code we write today will come back to haunt us later. With every line comes a cost. It's best to avoid writing any more than necessary. Code that doesn't exist cannot break and cannot hurt us. When writing it, be clear, be concise, and avoid being clever. 