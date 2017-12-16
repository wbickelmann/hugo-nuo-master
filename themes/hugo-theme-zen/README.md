# The Hugo Zen theme

**Zen** theme strives to be as clean and standard compliant as possible with some neat features. A solid base for your custom [Hugo](https://gohugo.io/) theme.

It uses HTML5 with a modern CSS grid and flex layout. Recent versions of all the mayor browsers support it, see [Can I use css grid](http://caniuse.com/#search=grid).

This is a port of the [Zen](https://www.drupal.org/project/zen) theme by [JohnAlbin](https://www.drupal.org/u/johnalbin), a very popular base theme for Drupal.

The [old branch](https://github.com/frjo/hugo-theme-zen/tree/old) has the original Zen grid system that uses floats and clearfixes like they did in the stone age.

## Features

* A mobile menu
* Analytics with Piwik
* Automatic linting of css and js
* CSS grid and flex for layout
* Gulp.js
* HTML5
* jQuery 3
* libSass
* Minify css
* Multilingual (i18n)
* Normalize CSS
* Responsive design
* RSS and JSON feeds with full content
* Search with DuckDuckGo

## Sites using the Hugo Zen theme

* [Combonetwork development](https://combonet.se/)
* [Drejargården](https://www.drejargarden.se/)
* [Helmer Grundström](https://www.helmergrundstrom.se/)
* [xdeb.org](https://xdeb.org/)

## On the large screen

![screenshot](https://raw.githubusercontent.com/frjo/hugo-theme-zen/master/images/tn.png)


## On the small screen

![screenshot](https://raw.githubusercontent.com/frjo/hugo-theme-zen/master/images/tn_mobil.png)


## The mobile menu

![screenshot](https://raw.githubusercontent.com/frjo/hugo-theme-zen/master/images/tn_mobil_menu.png)


## Installation

```
$ cd themes
$ git clone https://github.com/frjo/hugo-theme-zen.git zen
```

[Hugo - Installing Hugo](https://gohugo.io/getting-started/installing/)


## config.yaml example

All the "params" are optional.

```
baseurl: "https://example.org/"
title: "SiteTitle"

params:
  cacheBustCSS: true    # Add a cache busting hash on styles.css
  cacheBustJS: true     # Add a cache busting hash on script.js
  contact: "info@example.org"
  copyright: "This site is licensed under a 
              (https://creativecommons.org/licenses/by-sa/4.0/)."
              [Creative Commons Attribution-ShareAlike 4.0 International License]
  dateformat: ""        # Set the date format, default to "2 January, 2006"
  favicon: ""           # Relative path to favicon in json feed, no leading slash.
  feedlinks: true       # Show feed links in the footer.
  footer: "A [example.org](https://example.org/) production."
  icon: ""              # Relative path to icon in json feed, no leading slash.
  imageMaxWidth: ""     # Max width for images added via figure shortcode.
  jquery: true          # Add jQuery
  languageDir: ""       # Set ltr or rtl, defaults to ltr.
  logo: false           # Turn off the logo.
  mobileMenu: true      # Turn on a mobile menu on small screens.
  piwikSiteId:          # Piwik site id
  piwikTrackerUrl: ""   # Piwik url, schemaless and no slash on end (example.com/piwik).
  poweredby: true       # Show powered by hugo in footer
  search: true          # Site search with DuckDuckGo.
  searchSize: 20        # Search field size, default 20.
  sidebar: true         # Show a sidebar to the right
  submitted: true       # Show author and date information for a post.
```


## Dates

If "lastmod" is set in the frontmatter on a post that value will be used in the "submitted" section. If not "date" is used.

With "lastmod" set a date section will also appear at the bottom of post telling the reader the created and modification dates.


## Shortcodes

### Figure

Zen comes with a improved version of the built in "figure" shortcut.

* You can set a max width for images with parameter "imageMaxWidth". 
* If width and height is not set the real dimensions of the image will be used.
* If only width or height is set the other value will be proportionally calculated.

### Clear

Break float.

```
{{% figure src="/images/image.jpg" class="right" %}}

blablabla # Displayed left of the image.

{{% clear %}}

blablabla # Displayed below of the image.
```

## Use Gulp to generate css from sass

Your new Zen theme uses Gulp.js as a task runner, so that it can do many
different tasks automatically:

* Build your CSS from your Sass using libSass and node-sass.
* Add vendor prefixes for the browsers you want to support using Autoprefixer.
* Build a style guide of your components based on the KSS comments in your Sass
source files.
* Lint your Sass using sass-lint.
* Lint your JavaScript using eslint.
* Minify the css.
* Watch all of your files as you develop and re-build everything on the fly.

Set up your front-end development build tools:

1. Install Node.js and npm, the Node.js package manager.

    Detailed instructions are available on the "npm quick start guide":
    https://github.com/kss-node/kss-node/wiki/npm-quick-start-guide

2. The package.json file in your new sub-theme contains the versions of all the
Node.js software you need. To install them run:

        npm install

3. Install the gulp-cli tool globally. Normally, installing a Node.js globally
is not recommended, which is why both Gulp and Grunt have created wrapper
commands that will allow you to run "gulp" or "grunt" from anywhere, while
using the local version of gulp or grunt that is installed in your project.
To install gulp's global wrapper, run:

        npm install -g gulp-cli

5. The default gulp task will build your production minified CSS,
build your style guide, and lint your Sass and JavaScript.
To run the default gulp task, type:

        gulp

    To watch all your files as you develop, type:

        gulp watch

    or just type:

        gulp watch:css
  
    to only watch the css files.
