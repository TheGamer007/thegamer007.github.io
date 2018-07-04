---
title: Modifying the NavBar
prev: /docs/add_about
---

# Modifying the NavBar for smaller screens

The default CSS provided by my current _Architect_ theme has two blocks on the bottom that use the `@media` rule in order to figure out the dimensions of the screen being displayed, and then modify the styles accordingly. However, while most components / styles were handled well, the `aside` which served as my navbar was simply being resized to fit 100% width and have no `min-height`, so that it would go above the main content.

Since the list itself still remained vertical, this gave off a very weird looking UI. I attempted to use some of the popular CSS frameworks like `materialize` or maybe even other Github Pages themes, in order to provide a collapsible and swipeable drawer. I was against switching themes, and while `materialize` did have what I was looking for, my lack of prior web dev experience made the task seem less trivial than it probably is.

So I decided to keep it simple for now, and fiddled a bit with the `li` tags within the `aside` container. By setting their `dispay` property to `inline` rather than `block`, they do not break the line and appear neatly in a horizontal line. Since the usual padding of `30px` from the header block seemed a bit large on smaller screens, I halved it to `15` and it looked satisfactory.

At this point, there are two main changes I still want to do to the structure of the site. First is to change the NavBar into one adherent to Material Design that would work well with both web and mobile.

Secondly, adding some commenting or feedback mechanism to posts in order to gauge views and responses of site visitors. While you're always welcome to open an issue in the project's [Issues section](https://github.com/TheGamer007/thegamer007.github.io/issues) that limits it to users with a Github account.

I've avoided Disqus till now due to the privacy / visitor tracking concerns but most open-source, anon commenting solutions are slightly above my current comfort zone. In addition, I'd have to handle server requirements, and storage of the comment data, which will likely be inefficient and not ready-to-scale in my first attempt.

Of course, when I do get around to making any change, I'll add a corresponding post to the Docs section.
