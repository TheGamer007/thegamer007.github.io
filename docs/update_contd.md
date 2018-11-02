---
title: Polishing the update
parent: docs/index.md
menu: false
prev: /docs/update_to_v2
date: 03 November 2018
---

Not too long after eagerly making the last post and pushing changes, I was greeted with emails from GitHub informing me that the page builds were failing. Due to choosing the Architect theme the first time around, I was treating the new theme like a default one too. The issue was resolved by properly using the [Remote Theme](https://github.com/benbalter/jekyll-remote-theme) plugin as mentioned in the docs. The previous post wasn't incorrect, so anyone who follows the steps properly (unlike me), should be fine.

I went a step further and took a look at [Simple Jekyll Search](https://github.com/christian-fei/Simple-Jekyll-Search), the library that my theme was using for its search feature. Unlike back then, when it only searched the title and content, the library now supported tags, categories and date as well. So I migrated the changes to the new code into my `search.json` file, and updated my `default` layout to display the published date on top, while I was at it.

Thanks to those repeated fails, I feel I have a much better understanding of how the Jekyll build system works now, which will no doubt lead to a more polished site in the future.
