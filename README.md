# Jekyll Foundation Netlify

Quickstart your Jekyll (v3) project with Zurb Foundation for Sites (v6, sass) and Netlify CMS.

## Getting Started

1. Agree to Xcode terms with: `sudo xcodebuild -license`
1. Install [Homebrew](https://brew.sh/) `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`
1. Install [Ruby and Ruby Gems](https://rvm.io/rvm/install) with: `brew install ruby`
1. Install [Jekyll](http://jekyllrb.com/) with: `gem install jekyll`
1. Install [Bundler](http://bundler.io/) with: `gem install bundler` (mac users may need to install with `sudo gem install bundler`)
1. Install [Node.js](https://nodejs.org/en/)
1. Install [Yarn](https://yarnpkg.com/en/) with: `npm install --global yarn`

You only need to do these instructions once per machine.

## Installation

```bash
$ # Clone this repository
$ git clone https://github.com/kennedyrose/jekyll-foundation-netlify your-project-name

$ # Then navigate to the project directory
$ cd your-project-name

$ # Install all Ruby dependencies for the project
$ bundle install

$ # Install all Node dependencies for the project
$ yarn

$ # Create a new Github repository and point your local copy there
$ git remote set-url origin git@github.com:your-project-repo
```

You only need to do this once after cloning the repository.

## Development

Start development on your local machine with: `yarn dev`.

You can stop the development task by pressing <kbd>ctrl</kbd>+<kbd>c</kbd> in the terminal.

## Useful File Locations

### HTML
- `_layouts/index.html`: The template used for the home page.
- `_layouts/page.html`: The template used for all pages.
- `_layouts/post.html`: The template used for all blog posts.
- `_includes/head.html`: This content will be placed at the top of every page. Includes the `<head />` content
- `_includes/footer.html`: This content will be placed at the bottom of every page.

You can also create additional layouts for other page types you create in the `_layouts` directory.

### Page Content

All page content is written in [Markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet). The markdown is converted to HTML and can still be styled like you normally do with CSS.

Pages are located in the `_pages/` directory.

There are variables at the top of each `.md` file that will direct the system on which layout to use (from `_layouts/`), what the title of the page is and what the URL of the page should be.

The top of a markdown file might look something like this:

```markdown
---
permalink: /about-us/
layout: page
title: About Our Company
---
```


### Blog Posts

Blog pages are pretty much identical to standard pages.

They are located in the `_posts/` directory.

The only difference is that blog posts have the date prepending the file name. So a blog file name might look something like:

`2016-03-22-first-post.md`

Dates are formatted as `year-month-day`.

### Sass

The main Sass file is located in `assets/scss/app.scss`. The other directories in `assets/scss/` optionally show you how you can keep your Sass files seperated for more managable code.

If you do create a new Sass file, make sure to import it in the `app.scss` file or it will not get transpiled into CSS and therefore not exist on the site.

### Images

Images should go in the `assets/img/` directory. The URL will stay the same, so you can place images in your templates with:

`<img src="/assets/img/your-image.jpg" />`

Images are not compressed or resized in any way. So make sure to do your optimizations during development.

### Foundation Settings

By default, most of the Foundation settings are turned off to reduce the size of the JS and CSS files that are output. To turn on the features you need, uncomment lines of Sass located in:

`assets/scss/foundation/_foundation.scss`

If the feature you are trying to enable requires JavaScript as well, you can uncomment the feature in:

`gulp/config.yml`

## Deployment

Deployment through Netlify is fairly simple. [Signup/login at their website](https://www.netlify.com/) and just follow the instructions. You will basically just tell Netlify where your website repository is and it will do the rest of the work. Use the following settings when asked:

- Build command: `gulp build --production`
- Publish directory: `_site/`

## Editing Content with Netlify CMS

Netlify CMS offers a better way for non tech-savvy clients to edit their website's content.

To enable Netlify CMS, follow the instructions on [Authenticating with Github](https://www.netlifycms.org/docs/quick-start/).

Once that's done, you can go to `yoursite.com/admin` and just login through Github to edit content. You will set up each client with their own Github account and perform the authentication step to make sure they have access.

## Additional resources
- [Foundation Docs](http://foundation.zurb.com/sites/docs/)
- [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
- [Jekyll Docs](http://jekyllrb.com/docs/home/)
- [Netlify CMS Docs](https://www.netlifycms.org/docs/)
- [Original Repository](https://github.com/core77/jekyll-foundation)
- [Original Documentation](https://github.com/core77/jekyll-foundation/wiki/Getting-started)
