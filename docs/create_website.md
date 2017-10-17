---
title: Creating a website using GitHub Pages
next: /docs/customise_website
---

# Creating a website using GitHub Pages

The actual setup of the website using Github Pages is left to the detailed guides already provided by Github. I simply point out some helpful tips and give more details for the Local Jekyll setup, especially the installation on Windows.

## Initialisation
The GitHub repository was made as described in the GitHub Pages documentation for making a User or Organisation Page. The theme for the site can be selected through the Theme Chooser in the Github Pages section of the repository settings. (more on this in the next post)

This will generate two files: `_config.yml` and `index.md`. These two files are used along with Jekyll to render the actual Github Pages site. This much is enough for the site to go live, with content for the single page being taken from the `index.md` file.

### Local Jekyll Setup
Since the actual site is updated only when the corresponding files in `master` are changed, we need some way to test out minor edits before performing a final commit.

> Note: Adding [this gitignore file](https://gist.github.com/bradonomics/cf5984b6799da7fdfafd) to your repo before proceeding with the installation would prevent you from accidentally adding unnecessary files to the workspace.

[This guide](https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/) provides step-by-step instructions on how to setup a local Jekyll installation.
Once complete, we can view the site on `localhost:4000` or a similar location. Since I was developing on Windows, there were some additional steps needed to properly setup Jekyll as well as other necessary components. All neccessary links are there in the previous guide itself.
However, I would suggest using Linux or MacOS if you plan to invest heavily into your site, because some Jekyll features such as autogeneration are limited in Windows, not to mention the hassle-free installation process in those operating systems.

Once the installation is complete, but before running the `bundle exec jekyll serve` command, you should have one `Gemfile` and one `Gemfile.lock` in the root folder. If you already added the earlier `.gitignore` file, you can see that the `Gemfile.lock` file shouldn't be added to your workspace, or pushed to remote.
Similarly, the `_sites/` directory - which is generated within the root directory when the `bundle exec jekyll serve` command is run - should **not** be included in your workspace.

This is because Github Pages uses the same process on your files to generate the website, and it does not need the compiled `_sites/` folder to be included in your repository. Including it in the repo can lead to unexpected results.

Thus, the changes you need to make are supposed to be in the files **outside** the `_scripts/` dir. Jekyll will automatically modify those files when you modify the source files.
