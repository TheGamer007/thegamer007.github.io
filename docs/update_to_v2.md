---
title: Updating the blog to v2.0
parent: docs/index.md
menu: false
next: /docs/update_contd
date: 02 November 2018
---

It's been a long time since I updated the blog, so I decided to go a step further and try giving it an overhaul. As you can see, the results are promising.

Version 2.0 of the site is based on the [Jekyll MaterialDocs](https://github.com/chromatical/jekyll-materialdocs/) theme, which provides a lot of the features I've been looking for - a clean UI based on Material Design, a navigation drawer that is collapsible on smaller screens, and a search feature. Though the base theme seems to be ill suited for reading on mobiles due to the small font size, the required adjustments should not be a big deal.

In addition, I've also stumbled across a great solution for my comments problem. Behold [Staticman](https://staticman.net/), a free and open-source solution that brings user-generated content, like comments and reviews, to static sites. It is also extremely suited to the GitHub Pages + Jekyll model, and it stores all the comment data in the repository itself. I'll mostly stick to the default public instance, but for those willing to go the extra mile, one can easily set up their own instance by cloning the repo.

I'm really excited about attempting to integrate it with my site, and I also plan to experiment with the additional features it offers like the integrations with [Akismet](https://akismet.com/) for spam filtering, and [MailGun](MailGun) for email notifications. As always, I'll make another blog post with the details when I make the changes.
