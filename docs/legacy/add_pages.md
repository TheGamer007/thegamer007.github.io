---
title: Adding webpages to your website
parent: docs/legacy.md
prev: /docs/legacy/customise_website
next: /docs/legacy/add_navbar
---

Having lots of content on one page isn't good UX. Most websites are collections of webpages interconnected through hyperlinks. This way, you can group them into headings such as "Posts", "Documentation", "Support" etc. and make it easier for visitors to understand the layout of your site.

It is fairly simple to add a new page using Jekyll. Since it renders HTML pages from Markdown files, all you have to do is add a new markdown file with the content you require. Since visitors do not know how many pages your site has, or the names of files, they cannot visit pages without proper navigation. Multiple topologies are possible for the flow of navigation between your pages. A common case would be providing either a sidebar or a list of hyperlinks that connect all pages of the site in the `/index.md` file, which is loaded for the base URL.

><br/>
Jekyll makes blogging easier by providing plugins/themes and some built-in functionality that automatically adds posts to the site when a new file is created. This involves saving them to an `_posts/` directory and the filenames being the date of the post. My post however, covers manual addition and linking of pages. You can find more info about the former in the Jekyll Docs.

#### Making the page

Providing a link without a corresponding file being present would lead to a Not Found error. Thus, we will first make our post. Create a file called `page1.md` in the root directory.

Firstly, add the YAML Front Matter. This is the set of `---` at the top of your Markdown file. It is completely fine to leave it blank, but as mentioned earlier, adding at least a `title` parameter would be preferable. Parameters whose value is not specified will use the default values based on your Theme. For example the `layout` parameter uses `default.html` if none specified, but you can pass a custom file.

Then, after adding some content, your file should look something like this:

{% highlight markdown%}
---
title: Page 1
---

This is the first page we're adding to our site.
{% endhighlight %}

Now that we have our page ready, we can add a link to it in our `/index.md` file.

#### Linking Pages

Usual markdown syntax for adding Hyperlinks is all that is needed. The clickable text is placed in `[]` and the URL is placed in `()` adjacent to it. So, the code to redirect to google.co.in on clicking [this](https://google.co.in) is:

{% highlight markdown%}
[this](https://google.co.in)
{% endhighlight %}

While we can provide the complete URL to our new page, it is much easier to use relative addressing. So, to link our new page we can simply use `(/page1.md)` instead of `(https://username.github.io/page1.md)`. In case you would like to group files into folders rather than having them all in the root directory, you simply need to update the relative path. The pages in the Docs section of this site are all in the `docs/` folder, and hence the link becomes `/docs/page1.md`

#### Usage of `index.md` files

The corresponding URL for a page1.md file in the `docs/` dir would be `username.github.io/docs/page1` . So what would happen if you tried to manually navigate to `username.github.io/docs/`?

The answer is that it would simply display the directory structure, i.e a list of all files in the dir. However, we've also seen that `username.github.io` loads `index.md` without needing to have the filename suffixed. This is because files with the name `index` are treated specially. If we add another file named `index.md`, but this time in the `docs/` dir, then we would open this instead of the list of files we encountered earlier.

While proper linking of pages would never result in the appearance of this page, it might be in your best interests to foolproof the website from visitors who type the wrong URL. Since the file tree page has no formatting whatsoever, it sticks out like a sore thumb from the rest of your site. The `index` file helps you to present a formatted version of the tree which is in-line with the theme of the rest of your website.
