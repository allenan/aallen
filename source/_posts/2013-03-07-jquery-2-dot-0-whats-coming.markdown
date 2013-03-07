---
layout: post
title: "jQuery 2.0: What's Coming?"
date: 2013-03-07 12:12
comments: true
categories: [jQuery]
---

The second beta of jQuery's milestone 2.0 release, which addressed feedback from their first round of beta testing, was announced on March 1st, so we can anticipate a stable production-ready release to ship any day now. jQuery's popularity has risen consistently since its initial release in 2006 and can currently be found on 62.6% of websites according to [builtwith.com](http://trends.builtwith.com/javascript/jQuery). So what can we expect from this new release of the internet's most-used javascript library?

<!-- more -->

## No love for IE
As was announced several months ago, jQuery 2.0 will be making the controversial decision to drop support for versions of Microsoft Internet Explorer prior to version 9. Some developers are calling this a premature decision, while others bemoan relying on User Agent sniffing in the form of conditional comments for handling degradation to earlier versions. Others still laud this as an important step in the right direction. Their blog reassures those developers who are tasked with the unfortunate onus of supporting earlier versions of IE that new releases to jQuery 1.9 will still support IE 6, 7 and 8. They offer the following code snippet which we should expect to soon become ubiquitous, for better or worse.

``` html jQuery 2.0 fallback for IE http://blog.jquery.com/2013/03/01/jquery-2-0-beta-2-released/
<!--[if lt IE 9]>
    <script src="jquery-1.9.1.js"></script>
<![endif]-->
<!--[if gte IE 9]><!-->
    <script src="jquery-2.0.0b2.js"></script> 
<!--<![endif]-->
```
## "A Completed Refreshed Project"
IE controversy aside, what changes are coming and why should we upgrade?

According the the jQuery team in 2011:
{% blockquote %}
Our goal is to have a completely refreshed project with the 2.0 release. We will have a much simpler API, better stability, full documentation and a full test suite for every plugin.
{% endblockquote %}

So what has been done in the past two years to make good on those promises?

#### A Much Simpler API
With the new API comes the death knoll for many of the "deprecated and dubious features" that had crept into previous versions of jQuery. This new release sports a simpler and more streamlined API resulting in an overall size reduction of more than 10%. The new 1.9 release will share the same API as the 2.0 release so exact details regarding these changes can be found in the [jQuery 1.9 upgrade guide](http://jquery.com/upgrade-guide/1.9/). There is also a new, minimal selector engine that has been implemented by Richard Gibson. Although it is much cleaner and faster and can be used as a replacement for the Sizzle selector engine, there are major differences in the selectors and semantics that developers will need to watch out for.

#### Modular by Design
One of the most groundbreaking aspects of the 2.0 release will be the ability to roll your own jQuery without worrying about dependency. Projects like require.js that promote Asynchronous Module Definition (AMD) have gained quite a lot of traction over the past few years and for good reason. Loading your resources via AMD means only having to load what is needed by a given context. In this same vein, jQuery 2.0 now allows for custom builds through the use of a grunt build script. Each aspect of the jQuery library has been designed to be modular and handle decencies meaning that you can now build a custom version of jQuery for each project, requiring only the functions of the library that are needed. This will result in huge size reductions and performance increases.

#### A Central Plugin Registry
The jQuery team recently announced their initiative to create a [central plugin registry](http://plugins.jquery.com/) which will be a welcome relief for anyone that's had to track down the most recent version of a plugin across multiple home pages and GitHub repos. Speaking of GitHub, the plugin registry uses GitHub's post-receive webhook to publish a plugin. Nice to see they aren't trying to reinvent the wheel as far as central repositories go, but are rather building on top of the web's de facto place to store code.


## When to upgrade?
As with any big new release, it is probably prudent to resist the temptation of early-adoption, especially on high-profile sites. Despite thorough beta testing, there will certainly be some bugs that arise, and the conditional IE fallback may cause issues. But the jQuery team is not expecting the average site owner to upgrade immediately; their most recent blog post urges that 2.0 is currently best utilized for Chrome plugins, Firefox & Chrome OS apps, phonegap/cordova apps and other applications with contained browser environments. Despite these warnings, I can predict that many hasty site owners will be dropping in the 2.0 conditional on day one and we'll just have to sit back and see what happens…