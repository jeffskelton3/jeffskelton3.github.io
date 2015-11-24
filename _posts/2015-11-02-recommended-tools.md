---
layout: post
title: Recommended Tools
categories: [programming]
tags: [tools]
published: True

---
[Programmers are notoriously opinionated](https://www.reddit.com/r/java/comments/28e404/best_ide/). Be it the language we write in, the pens and notebooks we use, or the movies we like. If it exists and is to be geeked upon, we will do it. There is probably no place where that is true more than with the tools we use to get our day to day tasks done. Every programmer thinks he or she has the right set up and will chew your ear off telling you why. In my opinion, the tools that matter are the ones that one comes back to day after day. After years of experimenting I've narrowed my perfect tool belt down to the following.

### IDE: [WebStorm](https://www.jetbrains.com/webstorm/)

<a href="https://www.jetbrains.com/webstorm/" target="_blank" class="post-image-left"><img src="https://pbs.twimg.com/profile_images/582936156976775170/SZguGbqk.png" width="100" height="100" alt="WebStorm Logo"></a>

If you write primarily JavaScript and NodeJS like me, it's hard to overstate how useful this IDE from JetBrains is. The autocomplete alone blows the competition out of the water and there are simply no other debuggers that can touch it. It's available for Linux, OSX, and Windows and extensible with a huge ecosystem of plugins. The "find anything" double shift key command is simple and elegant and the refactoring tools are powerful enough to rival strongly typed languages (most of the time....). The new subscription model being introduced has me a bit concerned but the truth is that I upgrade every year anyways so it's a non issue.

---


### General Purpose Text Editor: [Sublime Text 3](http://www.sublimetext.com/3)

<img src="https://cdn.tutsplus.com/net/uploads/legacy/1140_st2plugins/200u.jpg" width="100" height="100" alt="">

As much as I love WebStorm it's a bit heavy for quick and dirty edits. That's were ST3 comes in. In fact, until very recently this was my code editor of choice and there are times where I miss it's combination of light weight speed and infinite configurability. To me, ST3 is the logical evolution of vim. You can use it for pretty much anything and with its powerful package manager you can configure it to behave pretty much any way you can dream up. If you aren't sure what editor to go for this would be my recommendation.

---


### Local Development Environment : [Docker](https://www.docker.com/)

<img src="https://www.docker.com/sites/default/files/legal/small_v-dark.png" width="100" height="100" alt="">

When I started out, the phrase “works on my machine” was something that got tossed around a lot.  A developer would make some changes, check them in, other developers would integrate those changes and [LINK] everything would explode [LINK]. Pushes to production were nail biting affairs that more often than not had catastrophic failures due to some missing configuration detail that got forgotten (the mere site of a web.config file makes me shudder).The dev ops movement happened and things started getting a bit better. With tools like Chef, Puppet and Vagrant (and now Otto which I’ve not had a chance to try) and things started getting a bit better. When Docker came out I didn’t pay attention. I figured it was a Vagrant clone. It wasn’t until I got to work on a project with it that I saw the power and simplicity of it in action. Being able to code in the same environment that will be on your production server saves so many headaches. If you’ve not tried Docker yet, all I can tell you is that once you “get it”, you’ll never go back to the dark ages.

---

### Instant Messaging: [Slack](https://slack.com/)

<img src="http://www.geonetsolutions.co.uk/wp-content/uploads/2015/05/huge-slack-logo-on-white.png" width="200" height="100" alt="">

I honestly don't know how i got anything done in the dark days before Slack. I've heard it referred to as the operating system for communication and couldn't have stated it better. It's been adopted at my current job and we've literally not sent a single email since. It's incredible. Email is exclusionary by design. Only the people you address a message to get the information you are sending. Slack turns that concept on its head. Almost all communication at my company is done in the publicly viewable channels. The result is an open culture where transparency is the norm. That's not to say it doesn't have its problems. The incessant chatter can be distracting so one needs to be a bit more discriminating when he or she does or does not tune in. It's the closest thing to an email killer I've ever seen that said.

---

### Email Client: [Airmail 2](http://airmailapp.com/)

<img src="http://www.macupdate.com/util/iconlg/48173.png" width="100" height="100" alt="">

Ok ok ok, email sucks but you HAVE to deal with it still sometimes. ¯\_(ツ)_/¯. Over the years I’ve pretty much tried them all. Airmail is fast, customizable and the search is every bit as good as the gmail web app (the default OS X mail app is utterly useless in this area). It works with all mail accounts you throw at it and has excellent key commands. In fact, my only complaint is that its missing the “snooze” features of Mailbox.

---

### Terminal: [iTerm 2](https://www.iterm2.com/)

<img src="http://cdn.curvve.com/wp-content/uploads/2013/10/iterm-logo24.png" alt="" width="100" height="100">

As a developer I spend a ton of time working from the terminal. The default offering for OS X is not bad but iTerm 2 blows it out of the water. Its customization options are very robust and the ability to do split screens is just awesome when you are working on multiple remote SSH sessions at once. I run my installation with Oh My Zsh which adds things like theming and configurable autocomplete.

---

### Source Control: [Tower 2](http://www.git-tower.com/)

<img src="https://fournova-website-assets.s3.amazonaws.com/assets/img/tower_app_icon_512x512.png" alt="" width="100" height="100">

I once worked on a project where a developer on the team was editing an untracked copy of the source code for almost a year (long story). Every few months said developer would send me updates in a zip file that I would need to integrate into the main branch. There is simply no way I could have done that without Tower.

A lot of developers snicker at the idea of using a GUI to manage their local git repos and I firmly believe every developer should at least know the basics of how to add, stage, commit, pull etc from the command line. When it comes to something more complex like, reviewing changes or managing merge conflicts, I prefer to use something that helps keep the whole tree clear in my head. WebStorm has a built in VCS management GUI as well but Tower just does it better and I’m not locked into just that one IDE.

---

### Password Manager: [1Password](https://agilebits.com/onepassword)

You need a password manager. Yes, you do. Humans can only remember so much and we are all guilty of re-using the same passwords and/or using insecure, easy to crack, passwords. When you are a developer it gets even more tricky. There is money on the line and you have literally hundreds, if not thousands of passwords to remember and deal with over the course of your career. 1Password makes managing all of that a breeze. Its encrypted, fast, and the browser extensions make using it nearly painless. It has an excellent password generator which takes the hassle out of coming up with a truly uncrackable password. My one criticism is that the iOS app is a bit on the clunky side (to really get the most out of it, one needs to use the built in browser but more apps are integrating it into their login flow. Most notably, Slack).

---

### Task Management: [Trello](https://trello.com)

<img src="https://s3.amazonaws.com/trello/images/og/trello-icon.png?v=2013-08-15" alt="" height="100" width="100">

If you’ve never heard of a kanban board, this scene from Silicon Valley does a wonderful job of explaining it.

<iframe src="https://player.vimeo.com/video/122563698" width="500" height="281" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

I use this tool with my team every day to track progress on a multitude of projects. I never have to worry about stepping on another developers toes since I can simply look in the “doing” column for a given board and see who’s working on what. Whats even better is that designers can drop in assets and links and we can have whole discussions about a task via the comments.

---

### Notes/Writing/Bookmarking/Study: [Evernote](https://evernote.com)

<img src="https://lh5.ggpht.com/u_ZwBnOs3s7nHA2v4XDCrJknAAVVHQIzK4mVF8tbx1n62-_LrDSopwHviqeNuDIFigc=w300" alt="" height="100" width="100">

[Theres been a lot said about Evernote recently](http://finance.yahoo.com/news/inside-story-1-billion-evernote-184047479.html) and a lot of the criticism I agree with. Its a bloated mess in some regards with cobbled on features that no one asked for or wanted ([just check out this forum post about the much maligned work chat feature to get an idea of what I mean](https://discussion.evernote.com/topic/73743-how-to-turn-off-work-chat/)). There are a lot of competitors out there so why do I still think its the best out there? Simple: searchable image text. That one feature means that I can completely digitize my entire office and be able to search for it. Without that feature I would have to deal with the mental overhead of needing to create some sort of taxonomy to sift through the literally thousands of notes that I’ve created over the years. There are other features that I use every day like the web clipper and the email to evernote feature but those I could live without. That search is simply irreplaceable so I deal with the bloat and just pretend that work chat is a bad dream.

_Side note: for most of my actual note taking I use the excellent Alternote which syncs to my Evernote account flawlessly. Its what I wish Evernote would be._

---

### Honorable Mentions

I don’t use these apps every day but they are an important part of my work flow:

- Adobe Photoshop - Sketch is rad but we all know where the real work gets done
- Dropbox - Bloated and stale like Evernote but everyone uses it so…
- Ghostlab 2 - A super useful tool for rapid responsive front end development. A bit buggy but very useful.

So thats it! There are a ton of tools I've left off this list so I'll have to do a follow up for things like recommended packages and what not. That said, if you’ve not tried any of these tools I highly recommend you do. [Hit me up on Twitter](https://twitter.com/vikingpanicatk) if you have some recommendations you want me to check out.
