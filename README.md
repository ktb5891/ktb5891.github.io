<<<<<<< HEAD
# ⚠️ Unmaintained ⚠️

# Prologue - Jekyll Theme

[![Gem Version](https://badge.fury.io/rb/jekyll-theme-prologue.svg)](https://badge.fury.io/rb/jekyll-theme-prologue)

![Prologue Theme](assets/images/screenshot.png "Prologue Theme Screenshot")

This is Prologue, a simple, single page responsive site template from [HTML5 UP](https://html5up.net/prologue), now available as a blog-aware Jekyll theme from [Chris Bobbe](https://chrisbobbe.github.io). It features a clean, minimalistic design and a sticky sidebar with navigation-linked scrolling.

**Demo**: https://chrisbobbe.github.io/jekyll-theme-prologue/

# Added Features

* **Blogging and multi-page features you expect from Jekyll**
* Compatible with GitHub Pages
* **[Formspree.io](https://formspree.io/) contact form integration** - just add your email to the `_config.yml` and it works!
* Build your homepage with **custom scrolly sections** in the _sections folder
 * Set a **cover photo** for any section (not just the first), with alt text for screen readers and SEO
* Add your **social profiles** easily in `_config.yml`.
* Automatic search engine optimization (SEO) **meta tags** based on info you provide in `_config.yml` and frontmatter
* **Google Analytics** built-in; just put your [Tracking ID](https://support.google.com/analytics/answer/1008080?hl=en) in `_config.yml` as `google_analytics`
* Custom **404 page** (called 404.html; to activate, move it to your project directory).

# Installation

There are two ways to get started (choose one):

1. **Install the [jekyll-theme-prologue gem](https://rubygems.org/gems/jekyll-theme-prologue).** Instructions are in the [Jekyll docs](https://jekyllrb.com/docs/themes/#installing-a-theme). After running `bundle install`, you can find the theme files by running `open $(bundle show jekyll-theme-prologue)`.  A sample working `_config.yml` file ships with the gem; if you want to activate it, move it to your project's root directory. It will do nothing until you move it there, replacing the default `_config.yml` file.
2. **Fork or clone the [GitHub repository](https://github.com/chrisbobbe/jekyll-theme-prologue).** If you want to use [GitHub Pages](https://pages.github.com/), create a branch named `gh-pages`, and replace `theme: jekyll-theme-prologue` with `remote_theme: chrisbobbe/jekyll-theme-prologue` in the provided `_config.yml` ([GitHub Pages now supports open-source themes on GitHub](https://github.com/blog/2464-use-any-theme-with-github-pages)).

Next, make sure that `url` and `base_url` are set for your own website in `_config.yml`. For local testing, make them both blank. Add a photo avatar to your project, then set `avatar: path/to/your/avatar.jpg` in _config.yml; for example, `avatar: assets/images/avatar.jpg` (48x48 pixels works best). Poke around the sample `_config.yml` file to see how you can add your social profiles.

# Build your homepage

1. **Your `_config.yml` file must include the following line or your homepage won't work**: `collections: [sections]`. This tells Jekyll to look in the _sections folder (which you will create) for your content and render it all on one page.

2. **Create a `_sections` folder** in your project's root directory and start adding content to your homepage. Set a cover photo in any of the sections by adding `cover-photo: path/to/photo.jpg` and `cover-photo-alt: your alt text here` to the section's frontmatter. Sample content is provided in the [GitHub repository](https://github.com/chrisbobbe/jekyll-theme-prologue/tree/master/_sections).

All new sections should be added as html or Markdown documents in the `_sections` folder. The following section variables can be set with [frontmatter](https://jekyllrb.com/docs/frontmatter/):
- `title` (required)
- `order` (required; orders the sequence of sections on the page. Example: `1`)
- `cover-photo` (optional; sets a background image for the section. Example: `assets/images/banner.jpg`)
- `cover-photo-alt` (required if using a cover photo. Describes the photo for screen readers and SEO; e.g. "Dome of Light art installation, Kaohsiung, Taiwan")
- `icon` (optional; see [Font Awesome](https://fontawesome.com/icons) for icon codes. Example: `fa-github`)
- `icon-style` (optional; "solid" is default, "regular" for outline style icons, or "brands" for logos)
- `auto-header` (optional; "use-title" is default, "none" for no header, or custom header text)
- `hide` (optional; if `true`, the section won't appear)

# Start blogging!

Jekyll has great resources to get you started writing blog posts. Check out [this Jekyll Docs page](https://jekyllrb.com/docs/posts/) first. When you've written a post or two, copy the following into a new file in your project directory called `blog.html`, and you'll see a link to your blog from the homepage:

```
---
layout: blog
title: My Blog
---
```

-- and that's it!

# Add a page

To add a page, just make a new .html or .md file in your project directory. There's an example called `reading-list` [provided](https://github.com/chrisbobbe/jekyll-theme-prologue/blob/master/reading-list.md) with the GitHub repository. Add this frontmatter:

```
---
title: My New Page
layout: page
---
```

You can also set these page variables in the frontmatter, if you want:
- `subtitle`
- `order` (orders links in the nav menu, e.g. `1`)
- `icon` (optional; see [Font Awesome](https://fontawesome.com/icons) for icon codes. Example: `fa-github`)
- `icon-style` (optional; "solid" is default, "regular" for outline style icons, or "brands" for logos)
- `hide` (optional; if `true`, a link won't appear in the nav menu. All this does is remove the nav link; your page will still be served to anyone who has the URL.)

**This same set of frontmatter variables (including `title`) can also be set in `index.md` and `blog.html`.** You may want to give them titles, or hide the homepage link with `hide: true` if the homepage is the only page.

For advanced SEO, this theme also lets you add `permalink` (see [Jekyll Docs](https://jekyllrb.com/docs/permalinks/#where-to-configure-permalinks)), `robots` (string, e.g. "noindex, nofollow"), and `canonical` (boolean; true is default) to any page or post.

# Contributing

Please feel free to submit issues and feature requests!

# Credits

Thanks to @andrewbanchich for his many Jekyll adaptations of HTML5 UP's elegant themes, which helped and inspired me, and of course many thanks to HTML5 UP.

Original README from HTML5 UP:

```
Prologue by HTML5 UP
html5up.net | @ajlkn
Free for personal and commercial use under the CCA 3.0 license (html5up.net/license)


This is Prologue, a simple, single page responsive site template. It features a
clean, minimalistic design and a sticky sidebar with navigation-linked scrolling.

Demo content images* are courtesy of the ridiculously talented Felicia Simion. Check out
more of her amazing work over at deviantART:

http://ineedchemicalx.deviantart.com/

(* = Not included! Only meant for use with my own on-site demo, so please do NOT download
and/or use any of Felicia's work without her explicit permission!)

Demo banner images* courtesy of Unsplash, a radtastic collection of CC0 (public domain)
images you can use for pretty much whatever.

(* = Not included)

AJ
aj@lkn.io | @ajlkn

PS: Not sure how to get that contact form working? Give formspree.io a try (it's awesome).


Credits:

	Demo Images:
		Felicia Simion (ineedchemicalx.deviantart.com)
		Unsplash (unsplash.com)

	Icons:
		Font Awesome (fortawesome.github.com/Font-Awesome)

	Other
		jQuery (jquery.com)
		html5shiv.js (@afarkas @jdalton @jon_neal @rem)
		CSS3 Pie (css3pie.com)
		background-size polyfill (github.com/louisremi)
		Respond.js (j.mp/respondjs)
		jquery.scrolly (@ajlkn)
		jquery.scrollzer (@ajlkn)
		Skel (skel.io)
```
=======
# Centrarium [![Circle CI](https://circleci.com/gh/bencentra/centrarium/tree/master.svg?style=svg)](https://circleci.com/gh/bencentra/centrarium/tree/master)

A simple yet classy theme for your Jekyll website or blog. Customizable to fit your style or brand.

Built with these awesome libraries:
* [Bourbon][bourbon]
* [Neat][neat]
* [Bitters][bitters]
* [Refills][refills]
* [Font Awesome][fontawesome]
* [HighlightJS][highlightjs]
* [Lightbox][lightbox]

Here's a [demo](http://bencentra.com/centrarium). It also works on [GitHub Pages](http://bencentra.github.io/centrarium/). I also use it for [my own website][bencentra].

Inspired by dirkfabisch's [Mediator](https://github.com/dirkfabisch/mediator) theme, which I previously used for my own blog, as well as [Type Theme](http://rohanchandra.github.io/type-theme/).

Cover image by Chris M. Morris ([flickr][cover]).

## Features

This theme comes with a number of features, including:
* Easily customizable fonts and colors
* Cover images for your homepage and blog posts
* Pagination enabled by default
* Archiving of posts by categories and tags
* Syntax highlighting for code snippets
* Disqus integration for post comments
* Lightbox for viewing full-screen photos and albums
* Google Analytics with custom page name tracking
* Social media integration (Twitter, Facebook, LinkedIn, GitHub, and more)

## Installation

If you're just getting started with Jekyll, you can use this repository as a starting point for your own site. Just [download this project](https://github.com/bencentra/centrarium/archive/master.zip) and add all the files to your project. Add your blog posts to the `posts/` directory, and create your pages with the proper Jekyll front matter (see `posts.html` for an example).

If your site already uses Jekyll, follow these steps:

1. Replace the files in the `_includes`, `_layouts`, and `_sass` directories with those from this project.
2. Replace your `index.html` with the one from this project, and copy over the `posts.html` file as well.
3. Copy the contents of the `_config.yml` from this project in to yours, and update the necessary information.

Don't forget to install Jekyll and other dependencies:
```bash
# cd into project directory
cd centrarium
# install Bundler if you don't have it already
gem install bundler
# install jekyll, jekyll-archives, jekyll-sitemap, and jekyll-paginate
bundle install
```

## Stackbit Deploy

This theme is ready to import into Stackbit. This theme can be deployed to Netlify and you can connect any headless CMS including Forestry, NetlifyCMS, DatoCMS or Contentful. 

[![Create with Stackbit](https://assets.stackbit.com/badge/create-with-stackbit.svg)](https://app.stackbit.com/create?theme=https://github.com/bencentra/centrarium)

## Updating Header and Footer Links

Links in the header and footer are auto-generated. Links will be made for all files marked `category: page`, that have a title, and have the custom `main_nav` front-matter variable set to `true`. You can modify the rules for link generation in `_layouts/nav_links.html`.

## Updating Styles

If you want change the CSS of the theme, you'll probably want to check out these files in the `_sass/` directory:

* `base/_variables.scss`: Common values found throughout the project, including base font size, font families, colors, and more.
* `base/_typography.scss`: Base typography values for the site (see `typography.html` for a demonstration)
* `_layout.scss`: The primary styles for the layout and design of the theme.

### Important Variables

Here are the important variables from `base/_variables.scss` you can tweak to customize the theme to your liking:

* `$base-font-family`: The font-family of the body text. Make sure to `@import` any new fonts!
* `$heading-font-family`: The font-family of the headers. Make sure to `@import` any new fonts!
* `$base-font-size`: The base font-size. Defaults to $em-base from Bourbon (`bourbon/settings/_px-to-em.scss`).
* `$base-font-color`: The color for the body text.
* `$action-color`: The color for links in the body text.
* `$highlight-color`: The color for the footer and page headers (when no cover image provided).

## Configuration

All configuration options can be found in `_config.yml`.

### Site Settings

* __title:__ The title for your site. Displayed in the navigation menu, the `index.html` header, and the footer.
* __subtitle:__ The subtitle of your site. Displayed in the `index.html` header.
* __email:__ Your email address, displayed with the Contact info in the footer.
* __name:__ Your name. _Currently unused._
* __description:__ The description of your site. Used for search engine results and displayed in the footer.
* __baseurl:__ The subpath of your site (e.g. /blog/).
* __url:__ The base hostname and protocol for your site.
* __cover:__ The relative path to your site's cover image.
* __logo:__ The relative path to your site's logo. Used in the navigation menu instead of the title if provided.

### Build Settings

* __markdown:__ Markdown parsing engine. Default is kramdown.
* __inter_post_navigation:__ Whether to render links to the next and previous post on each post.

### Pagination settings

See the documentation for [jekyll-paginate-v2](https://github.com/sverrirs/jekyll-paginate-v2/blob/master/README-GENERATOR.md#site-configuration) for more details.

### Archive Settings

Although this theme comes with a combined, categorized archive (see `posts.html`), you can enable further archive creation thanks to [jekyll-archives][archives]. Support for category and tag archive pages is included, but you can also add your own archive pages for years, months, and days.

To change archive settings, see the __jekyll-archives__ section of `_config.yml`:

```yml
jekyll-archives:
  enabled:
    - categories
    - tags
  layout: 'archive'
  permalinks:
    category: '/category/:name/'
    tag: '/tag/:name/'
```

To fully disable the archive, remove the __jekyll-archives__ section AND remove it from the __gems__ list.

__NOTE:__ the Jekyll Archive gem is NOT included with GitHub pages! Disable the archive feature if you intend to deploy your site to GitHub pages. [Here is a guide](http://ixti.net/software/2013/01/28/using-jekyll-plugins-on-github-pages.html) on how you can use the `jekyll archive` gem with GitHub pages. The general gist: compile the Jekyll site locally and then push that compiled site to GitHub.

A sitemap is also generated using [jekyll-sitemap][sitemap].

### Syntax Highlighting Settings

Inside of a post, you can enable syntax highlighting with the `{% highlight <language> %}` Liquid tag. For example:

```
{% highlight javascript %}
function demo(string, times) {
  for (var i = 0; i < times; i++) {
    console.log(string);
  }
}
demo("hello, world!", 10);
{% endhighlight %}
```

You can change the [HighlightJS theme][highlightjs_theme] in `_config.yml`:

```yml
highlightjs_theme: "monokai_sublime"
```

### Disqus Settings

You can enable [Disqus][disqus] comments for you site by including one config option:

* __disqus_shortname:__ Your Disqus username. If the property is set, Disqus comments will be included with your blog posts.

If you want to disable Disqus for only a specific page, add __disqus_disabled: true__ to the page's front matter.

### Google Analytics Settings

You can enable basic [Google Analytics][ga] pageview tracking by including your site's tracking ID:

* __ga_tracking_id__: The Tracking ID for your website. You can find it on your Google Analytics dashboard. If the property is set, Google Analytics will be added to the footer of each page.

### Social Settings

Your personal social network settings are combined with the social sharing options. In the __social__ section of `_config.yml`, include an entry for each network you want to include. For example:

```yml
social:
  - name: Twitter                         # Name of the service
    icon: twitter                         # Font Awesome icon to use (minus fa- prefix)
    username: TheBenCentra                # (User) Name to display in the footer link
    url: https://twitter.com/TheBenCentra # URL of your profile (leave blank to not display in footer)
    desc: Follow me on Twitter            # Description to display as link title, etc
    share: true                           # Include in the "Share" section of posts
```

### Social Protocols

Using the Open Graph Protocol or Twitter Card metadata, you can automatically set the images and text used when people share your site on Twitter or Facebook. These take a bit of setup, but are well worth it. The relevant fields are at the end of the `_config.yml` file.

Also there is another protocol, the Open Source protocol, for saying where your site is hosted if the source is open. This helps develops more easily see your code if they are interested, or if they have issues. For more, see http://osprotocol.com.

### Category Descriptions

You can enhance the `posts.html` archive page with descriptions of your post categories. See the __descriptions__ section of `_config.yml`:

```yml
# Category descriptions (for archive pages)
descriptions:
  - cat: jekyll
    desc: "Posts describing Jekyll setup techniques."
```

### Custom Page-Specific Javascript

You can add page-specific javascript files by adding them to the top-level `/js` directory and including the filename in the __custom_js__ page's configuration file:

```yml
# Custom js (for individual pages)
---
layout: post
title:  "Dummy Post"
date:   2015-04-18 08:43:59
author: Ben Centra
categories: Dummy
custom_js:
- Popmotion
- Vue
---
```

The `/js/` directory would contain the corresponding files:

```bash
$ ls js/
Popmotion.js Vue.js
```

## Contributing

Want to help make this theme even better? Contributions from the community are welcome!

Please follow these steps:

1. Fork/clone this repository.
2. Develop (and test!) your changes.
3. Open a pull request on GitHub. A description and/or screenshot of changes would be appreciated!
4. I ([Ben Centra](https://github.com/bencentra)) will review and merge the pull request.

## License

MIT. See [LICENSE.MD](https://github.com/bencentra/centrarium/blob/master/LICENSE.md).

[bencentra]: http://bencentra.com
[bourbon]: http://bourbon.io/
[neat]: http://neat.bourbon.io/
[bitters]: http://bitters.bourbon.io/
[refills]: http://refills.bourbon.io/
[fontawesome]: http://fortawesome.github.io/Font-Awesome/
[highlightjs]: https://highlightjs.org/
[highlightjs_theme]: https://highlightjs.org/static/demo/
[lightbox]: http://lokeshdhakar.com/projects/lightbox2/
[cover]: https://www.flickr.com/photos/79666107@N00/3796678503/in/photolist-6MuYfc-61Rtft-8XzPmY-a6Cozm-54eSMs-6oMJmk-aepZQq-9YkPHp-fiAEGE-dVP4Z5-oxPyJP-atKUFJ-9YHWA5-9YF2f2-9YF2gR-9YHVGN-9YHVvs-qZYYQ6-4JqP2i-a2peGy-9YHVUm-9YHVF7-9YHVCL-9YF3NK-cYteMo-aiPmb9-69dtAi-9YF21x-4aWpmn-7SLiUL-77pqVX-8vXbYv-4HGDSH-a2h5P1-8LsZrQ-9aj1ez-auPZ7q-9YHVMd-9YF2bi-9YF23D-8LpWpn-9an6KL-9YHVZL-dqZ3Cz-2GuvnX-9YHWUo-9YHVWd-p5Roh5-i1zTbv-6sYrUT
[disqus]: https://disqus.com/
[ga]: http://www.google.com/analytics/
[archives]: https://github.com/jekyll/jekyll-archives
[sitemap]: https://github.com/jekyll/jekyll-sitemap
>>>>>>> 5fe7677ed013a8133ffd0896724772fa8a1178b4
