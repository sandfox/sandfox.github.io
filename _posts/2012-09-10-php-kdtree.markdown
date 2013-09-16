---
title: "A K-D Tree library for PHP"
layout: post
---

I've finally found the time to smarten up slightly a [k-d tree](http://en.wikipedia.org/wiki/K-d_tree) library for PHP that I decided to write a while ago after doing something similar in JavaScript and finding it quite interesting. So far I'm not aiming for speed, just a technically correct version. I suspect my overuse of classes and inefficient sort algorithms is what makes this dog slow (it's horrifically slow compared to c/c++/javascript implementations)

It's available at [packagist](http://packagist.org/packages/sandfox/kdtree) and can be installed via [composer](http://getcomposer.org/) `composer install sandfox/kdtree`

If you want to have a look at the source it's on [Github](https://github.com/sandfox/kdtree)

It's currently at version 0.0.2 and probably isn't that useful to anyone right now unless you happen to have the exact same usage case as seen in the example folder.

If anyone wants to contribute tests, docs, bugs or anything else feel free. Equally if you have any questions fire away via twitter or e-mail.
