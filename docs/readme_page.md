---
title: Documentation
---


This README details the making of this website, and can be a helpful resource for anyone wishing to implement some or all of the features I've added.

## Initialisation
The GitHub repository was made as described in the GitHub Pages documentation for making a User or Organisation Page. The theme for the site can be selected through the Theme Chooser in the Github Pages section of the repository settings.

This will generate two files: `_config.yml` and `index.md`. These two files are used along with Jekyll to render the actual Github Pages site. This much is enough for the site to go live, with content for the single page being taken from the `index.md` file.

### Local Jekyll Setup
Since the actual site is updated only when the corresponding files in `master` are changed, we need some way to test out minor edits before performing a final commit.

> Note: Adding [this gitignore file](https://gist.github.com/bradonomics/cf5984b6799da7fdfafd) to your repo before proceeding with the installation would prevent you from accidentally adding unnecessary files to the workspace.

[This guide](https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/) provides step-by-step instructions on how to setup a local Jekyll installation.
Once complete, we can view the site on `localhost:400` or a similar location. Since I was developing on Windows, there were some additional steps needed to properly setup Jekyll as well as other necessary components. All neccessary links are there in the previous guide itself.
However, I would suggest using Linux or MacOS if you plan to invest heavily into your site, because some Jekyll features such as autogeneration are limited in Windows, not to mention the hassle-free installation process in those operating systems.

Once the installation is complete, but before running the `bundle exec jekyll serve` command, you should have one `Gemfile` and one `Gemfile.lock` in the root folder. If you already added the earlier `.gitignore` file, you can see that the `Gemfile.lock` file shouldn't be added to your workspace, or pushed to remote.
Similarly, the `_sites/` directory - which is generated within the root directory when the `bundle exec jekyll serve` command is run - should **not** be included in your workspace.

This is because Github Pages uses the same process on your files to generate the website, and it does not need the compiled `_sites/` folder to be included in your repository. Including it in the repo can lead to unexpected results.

Thus, the changes you need to make are supposed to be in the files **outside** the `_scripts/` dir. Jekyll will automatically modify those files when you modify the source files.

## Customising the Page

### Customising metadata and seo tags

The content shown on the page is taken from the corresponding files, but the Title, Description and some other things such as the text displayed on the browser tab are determined by metadata.

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

### Customising content

> Note: The content can either be rendered from Markdown files, or from HTML files. If you use Markdown, Jekyll generates the HTML file that will render the webpage. **This site was made using Markdown files, and hence only covers the same process**

The content shown on your website is taken directly from the `index.md` file by default. The auto-generated `index.md` file has a lot of text demostrating the basic Markdown syntax. Jekyll then applies the default html and css formatting to your content based on your selected theme.

### Customising the layouts

While the theme default layouts are great, if you want to change any attribute such as formatting or if you want to remove some elements, you need to implement your own files.

Each theme has its own Github repo. For example, the theme I use is [Architect](https://github.com/pages-themes/architect). Once you find the repo, you will need to copy the contents of the `_layouts/` and `assets/` directories into your repo.

So the `_layouts/default.html` file from the theme repo goes into a corresponding `_layouts/default.html` file on your repo. And similarly with the `assets/`.

Once this is done, Jekyll will use these files to generate the page rather than the default theme files. So, any changes you make to these files will affect the way your site looks.

If you aren't that well-versed with web development, then keep in mind that the `default.html` file is the HTML file that will determine how your content is placed. You need to edit this to add new elements, or to remove ones that you don't need.

The `assets/css/styles.css` file provides CSS based style formatting to your HTML elements. This is where you can change the font colour, font size, and other properties that affect the visual of the site.
