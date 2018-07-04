---
title: Making of the About Section
prev: /docs/add_navbar
next: /docs/navbar_mobile_update
---

# Making of the About Section

Most websites have an 'About us' section where they have more information about them, rather than their products. It is an important section both for companies (which showcase their mission and vision) and individuals (who provide links to their other works and profiles). My main purpose in adding an about page was to have a single page I could point to whenever I wanted to showcase myself, rather than sending separate links for Github, LinkedIn etc.

## Layout

The layout html for the page is a slightly modified version of the default layout. The modifications include adding the profile image and the social buttons. Since centering text isn't easily achievable through simple markdown, the designation itself is also added to the HTML.

URLs for the profile picture and social buttons (taken from [here](https://github.com/janhuenermann/social-circles/)) are specified in the yaml frontmatter and loaded as variables in the HTML, making it slightly easier to edit. The reason I added my email address as an image rather than simple text is to avoid automated crawlers that might spam the id. This is on the slightly paranoid side though, and it isn't an issue if you choose to keep it simple and leave it in plaintext.
