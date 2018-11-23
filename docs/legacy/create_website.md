---
title: Creating a website using GitHub Pages
parent: docs/legacy.md
next: /docs/legacy/customise_website
---

The actual setup of the website using Github Pages is left to the detailed guides already provided by Github. I will simply point out some helpful tips and give more details for the Local Jekyll setup.

>I would suggest using Linux or MacOS if you plan to invest heavily into your site, because some Jekyll features (such as autogeneration) are limited in Windows. The following instructions will work for Ubuntu like Linux systems, and the Bash-on-Windows prompt on Windows.

#### Initialization
The GitHub repository was made as described in the GitHub Pages documentation for making a User or Organization Page. The theme for the site can be selected through the Theme Chooser in the Github Pages section of the repository settings. (more on this in the next post)

This will generate two files: `_config.yml` and `index.md`. These two files are used along with Jekyll to render the actual Github Pages site. This much is enough for the site to go live, with content for the single page being taken from the `index.md` file.

##### Local Jekyll Setup
Since the actual site is updated only when the corresponding files in `master` are changed, we need some way to test out minor edits before performing a final commit.

>Adding [this gitignore file](https://gist.github.com/bradonomics/cf5984b6799da7fdfafd) to your repo before proceeding with the installation would prevent you from accidentally adding unnecessary files to the workspace.

[This guide](https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/) provides step-by-step instructions on how to setup a local Jekyll installation. However, it misses out on some dependencies that it assumes are available on the user's system. So run the following commands first, then proceed with the earlier guide.

{% highlight bash %}
sudo apt-get install ruby ruby-dev libffi-dev clang zlib1g-dev
sudo apt-get install build-essential dh-autoreconf
{% endhighlight %}

Once complete, we can view the site on `localhost:4000` (by default) by running the appropriate command: `bundle exec jekyll serve`. Before running the command, you should have one `Gemfile` and one `Gemfile.lock` in the project folder. If you already added the earlier `.gitignore` file, you can see that the `Gemfile.lock` file shouldn't be added to your workspace, or pushed to remote.
Similarly, the `_site/` directory - which is generated within the project directory when the `bundle exec jekyll serve` command is run - should **not** be included in your workspace.

This is because Github Pages uses the same process on your files to generate the website, and it does not need the compiled `_site/` folder to be included in your repository. Including it in the repo can lead to unexpected results.

Thus, the changes you need to make are supposed to be in the files **outside** the `_site/` dir. Jekyll will automatically modify those files when you modify the source files.
