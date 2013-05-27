---
layout: post
title: "Learn Sass and Compass quick"
date: 2013-05-26 23:55
comments: true
categories: ["Tutorial", "CSS"]
tags:
- Sass
- Compass
---

For [Code Fellows](http://codefellows.org) we had to do a lightning talk on a topic of our choice. Since Rails utilizes Sass and my CSS skills have always been more of a learn on demand thing rather than a deep dive, I decided to check Sass out. While doing so, Compass came up often, so I added a little bit of it to my presentation.

Below are my slides, notes and links so you can play around with Sass. It's pretty easy to digest but there's a lot of depth I didn't cover and need to continue learning myself. Enjoy!

---

## Slides
<iframe src="http://www.slideshare.net/slideshow/embed_code/21581469" width="427" height="356" frameborder="0" marginwidth="0" marginheight="0" scrolling="no" style="border:1px solid #CCC;border-width:1px 1px 0;margin-bottom:5px" allowfullscreen webkitallowfullscreen mozallowfullscreen> </iframe>

## Compass and Sass examples
Try it out by installing compass, cloning the repo and then opening the application.css.scss file.

    gem install compass
    git clone git@github.com:bbshih/sass_presentation.git
    cd sass_presentation
    rake db:migrate db:test:prepare
    subl /app/assets/stylesheets/application.css.scss
    Start a rails server and load localhost:3000 in the browser.

## SASS = Syntactically Awesome Stylesheets

TL;DR Sass is an extension of CSS3 that adds on features that programming languages have that CSS lacks. These features make it easier to write and manage CSS.

### Sass filetypes

Sass has 2 acceptable syntaxes with 2 different file types:

 - Indented syntax(.sass) - Similar to Haml
 - SCSS(.scss) - Uses CSS semantics, so CSS is valid SCSS (I'll be using this in the demo)

Sass has an interpreter that spits out traditional CSS files from the *.scss files you create. You can set a command to monitor whenever you make changes to your .scss file so that you always have the .css file, but with Rails and the Sass gem, it will always automatically generate a .css file for you when you reload the page.

### Compass

Compass is an open-source CSS framework. It utilizes Sass to provide mixins that solve common problems encountered when creating CSS files

### How to install

Add to your Gemfile

    group :assets do
      gem 'sass-rails' # if running rails 3.1 or greater
      gem 'compass-rails'
    end

In your project directory run:

    $ bundle
    $ bundle exec compass init

Rename your `application.css` to `application.css.scss` to change it into a Sass file. Then add the import below to the file:

    @import "compass"

Create new .scss files and @import them into the application.css.scss to use them.

Once your ready to push for production use:

    rake assets:precompile

### Features of Sass

**Variables**

- Create a variable by using $name and assign value with a `$highlight: #ff0000;`

- Supports 4 data types: numbers (and units), strings, colors and booleans

**Nesting**

Place child styles within a parent for better organization and readability

**Mixins**

 - A selection of code that contains any valid Sass code. Whenever the mixin is called, it is inserted into the location
 - Define by using `@mixin nameOfMixIn {}` and then calling `@include nameOfMixIn`
 - You can give a mixin an argument to customize the mixin code:

        #mixin highlightBox($border_width) {
            border-width: $border_width
            color: blue;
        }

        .box {
            @include highlightBox(3px)
            height: 30px;
        }

**Selector inheritance**

Use CSS of another selector by using `@extend selectorName`
