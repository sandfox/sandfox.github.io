---
layout: post
title: "A Brave New World"
---

Woohooo - This is my first post using [Jekyll](http://jekyllrb.com/) (with some serious assistance from [Jekyll Bootstrap](http://jekyllbootstrap.com/))!

###Why the change?

After enough faffing about with Wordpress and feeling it was the non-developers answer to blogging combined with never quite summing up the energy to go publish anything using it I felt a change was in order. Now, a quick note before the Wordpress Mafia fire up the outrage bus. Wordpress is as CMS/Blogging software goes, pretty awesome. By and large it allows the non-web-developer world to get started with little technical knowledge and have a professional looking and easy to use site quickly, and this can only be seen as a good thing. However as a vaguely technical person, it's faffy to hack around with and I don't need 99% of its features. (And some of the codebase still looks the aftermath of a bomb in a alphabeti-spaghetti factory!)


###The Requirements

After doing some googling and seeing what all the other cool web kids (TM) were up to I decided the next solution needed to be simple and these were the vague requirements (by no means complete, exhaustive, logical or necessarily what I've ended up with):

#### No database (nope, not even anything NoSQL-ish)

It's boring to maintain DB servers for something as trivial as a blog, and without caching makes things slow. ALso every good engineer likes to remove the number of moving parts in a system as it tends to mean the run for longer before falling over.

#### Easy to backup

While what I have to say may not ever change the world, I'd like to keep hold of it and don't want a simple bit of hardware failure or attack of the fat-fingers to wipe everything out.

#### Simple to deploy and move around

The freedom and ease to move from one server to another, or one service provider is a must. You never know who will buy who or go bankrupt or decide to let the chaos monkey reign in their server racks.

#### Teach me something I don't currently know

Everyday should be a school day.

#### Customisation/plugins/css-hacks are not mandatory

I don't want to have to put in a huge amount of effort to hit the "minimum value product" point

#### Blog offline 

I spend alot of time commuting which is a good time to get writing , but mobile signal coverage on the train is largely non-existent. This shouldn't be a barrier.

#### Just let me blog!

I don't want to have alot of hurdles between thoughts popping into my head and something about those thoughts appearing on my blog.

#### Not be wordpress

This is the largely illogical one, but I've suffered enough wordpress extensions/themes pain for one lifetime.
 

###The Solution (so far)

All of the above seemed to point to using some form of static site generator. I'd come across these before but I'd never really delved because either I was feeling lazy at the time or I was having a delusional moment of being happy with wordpress. Then I came across [Github's pages](http://pages.github.com/), spent a few hours reading up about how they worked and what on earth Jekyll was, (thought about binning it becuase it was written in ruby) and in a stroke of divine intervention spotted a tweet about Jekyll-Bootstrap before I completely shelved the idea. It's only taken a couple of hours to get through the basic of getting it up and running on github (using CNAME for those wondering about the domain name). 
I still need to convert over my old blog posts, customise the theme ever so slightly to sate my need to be different, and possibly tidy up the whatever cruft Jekyll-Boilerplate leaves lying around.


