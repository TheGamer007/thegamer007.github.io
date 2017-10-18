---
title: Customising the website using Jekyll themes
prev: /docs/create_website
next: /docs/add_pages
---
# Customising the Website (using Jekyll Themes)

Now that you have the website up and running, it's time to take advantage of Jekyll's features in order to personalize the visuals and behaviour. As mentioned earlier, you can use a number of available Jekyll themes out-of-the-box in order to generate a website to your liking. However, if you wish to modify some of the behaviour provided, read on.

## Jekyll Themes

From the [Jekyll Docs](https://jekyllrb.com/docs/themes/):
> Jekyll has an extensive theme system that allows you to leverage community-maintained templates and styles to customize your site’s presentation. Jekyll themes package up layouts, includes, and stylesheets in a way that can be overridden by your site’s content.

Themes allow you to mirror the look and feel of the corresponding website by providing the relevant layouts and stylesheets, thus reducing the code you need to write. Since most themes have active contributors, you can be certain that basic functionality will not have any obvious bugs. The themes themselves are Open Source, and have Github repos.

### Adding a theme

Go to the Settings section of your repo and scroll down to the **Github Pages** heading. This contains the status of your website, which branch it uses as the source to generate the site, the chosen theme and custom domain options. We are interested in choosing a theme.

Clicking the "Choose Theme" button provides a gallery of some of the popular themes. You can either select one of those, or choose another Jekyll theme of your choice. For instance, I chose the Architect theme from the default set. A detailed guide to add a theme can be found [here](https://help.github.com/articles/adding-a-jekyll-theme-to-your-github-pages-site/).

[This page](https://github.com/jekyll/jekyll/wiki/themes) from the Jekyll wiki provides a (non-exhaustive) list of all the themes that you can use in order to render your site.

## Customising various features

There are three primary areas which you would want to modify:
* The textual content of each post/page on the site
* The visual representation of this content (HTML/CSS).
* The metadata and SEO tags that affect online searches

### Customising content

> Note: The content can either be rendered from Markdown files, or from HTML files. If you use Markdown, Jekyll generates the HTML file that will render the webpage. **This site was made using Markdown files, and hence only covers the same process**

The content shown on your website is taken directly from the `index.md` file by default. The auto-generated `index.md` file has a lot of text demostrating the basic Markdown syntax. Jekyll then applies the default html and css formatting to your content based on your selected theme.

### Customising the layouts

While the theme default layouts are great, if you want to change any attribute such as formatting or if you want to remove some elements, you need to implement your own files.

Each theme has its own Github repo. For example, the theme I use is [Architect](https://github.com/pages-themes/architect). Once you find the repo, you will need to copy the contents of the `_layouts/` and `assets/` directories into your repo.

So the `_layouts/default.html` file from the theme repo goes into a corresponding `_layouts/default.html` file on your repo. And similarly with the `assets/`.

Once this is done, Jekyll will use these files to generate the page rather than the default theme files. So, any changes you make to these files will affect the way your site looks.

If you aren't that well-versed with web development, then keep in mind that `default.html` is the file that will determine how your content is structured. You need to edit this to add new elements, or to remove ones that you don't need.

The `assets/css/styles.css` file provides CSS based style formatting to your HTML elements. This is where you can change the font colour, font size, and other properties that affect the visual of the site.

### Customising metadata and seo tags

The content shown on the page is taken from the corresponding files, but the Title, Description and some other parameters such as the text displayed on the browser tab are determined by metadata.

This metadata is taken from two sources: The `_config.yml` file and the YAML Front Matter in each content file.

The `_config` file has overall site based tags, such as `title`,`author` and `description`. This `title` and `description` are the ones shown in the header of the default page.

YAML Front Matter is of the form
```
---
title: Home
layout: default
---
```
where the two `---` mark the start and end of the tags.

Assuming your `index.md` file provides the YAML `title` as "Home" and your site title in `_config` is "My Site", then the tab in your browser will display: " Home \| My Site ".

One good reason to set these tags is because leaving them as default would generate " Welcome to Github Pages \| username.github.io " by default; Something I did not find very catchy.
