# freistilbox Online Documentation

This repository contains the source documents for [docs.freistilbox.com](http://docs.freistilbox.com).

We use the [nanoc](http://nanoc.ws/) static site generator to build the website and Github Pages to host it.


## Setup

Get the repository

    git clone git@github.com:freistil/freistilbox-docs.git

Check out the `gh-pages` branch:

    git checkout -b gh-pages origin/gh-pages
    git checkout master

To install the necessary Ruby gems, execute the following commands in the `master` branch:

    gem install bundler
    bundle install


## Development

Nanoc compiles the site into static files living in `./output`.  It's
smart enough not to try to compile unchanged files:

    $ nanoc compile
    Loading site data...
    Compiling site...
       identical  [0.00s]  output/css/960.css
       identical  [0.00s]  output/css/pygments.css
       identical  [0.00s]  output/css/reset.css
       identical  [0.00s]  output/css/styles.css
       identical  [0.00s]  output/css/uv_active4d.css
          update  [0.28s]  output/index.html
          update  [1.31s]  output/v3/gists/comments/index.html
          update  [1.92s]  output/v3/gists/index.html
          update  [0.25s]  output/v3/issues/comments/index.html
          update  [0.99s]  output/v3/issues/labels/index.html
          update  [0.49s]  output/v3/issues/milestones/index.html
          update  [0.50s]  output/v3/issues/index.html
          update  [0.05s]  output/v3/index.html

    Site compiled in 5.81s.

You can setup whatever you want to view the files.  If you have the adsf
gem, however (I hope so, it was in the Gemfile), you can start Webrick:

    $ nanoc view
    $ open http://localhost:3000

Compilation times got you down?  Use `autocompile`!

    $ nanoc autocompile

This starts a web server too, so there's no need to run `nanoc view`.
One thing: remember to add trailing slashes to all nanoc links!

## Deploy

    $ rake publish

