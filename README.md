# freistilbox Online Documentation

This repository contains the source documents for [docs.freistilbox.com](http://docs.freistilbox.com).

We use the [nanoc](http://nanoc.ws/) static site generator to build the website and Github Pages to host it.


## Repository layout

First, check out the source branch:

    git clone git@github.com:freistil/freistilbox-docs.git

Then setup the nanoc `output` directory as branch `gh-pages`:

    git clone git@github.com:freistil/freistilbox-docs.git output
    cd output
    git checkout gh-pages


## Development tools

To install the necessary Ruby gems, execute the following commands in the source branch:

    gem install bundler
    bundle install


## Site update

Make your edits and generate a new website version from the source branch:

    nanoc

Second and last, push the updated files in the pages branch to Github:

    cd output
    git add .
    git commit
    git push

For more usage help see the [nanoc website](http://nanoc.ws/).
