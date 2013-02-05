# freistilbox Online Documentation

This repository contains the source documents for [docs.freistilbox.com](http://docs.freistilbox.com).

We use the [nanoc](http://nanoc.ws/) static site generator to build the website and Github Pages to host it.


## Repository layout

We use the same repository with its different branches `master` and
`gh-pages` to work around Githubs setup.  
`master` is for the sources. `gh-pages` is checked out in nanocs
output directory, so it's really easy to publish to Github.  
If you can wrap your head around using recursions on repositories. Which
@muhh couldn't, so he had to write these lines.

### Step-by-step 

First, check out the source branch:

    git clone git@github.com:freistil/freistilbox-docs.git

Then setup the nanoc `output` directory using the branch `gh-pages`:

    git clone git@github.com:freistil/freistilbox-docs.git output
    cd output
    git checkout gh-pages


## Development tools

To install the necessary Ruby gems, execute the following commands in the `master` branch:

    gem install bundler
    bundle install

## Site update

Make your edits and generate a new website version from the `master` branch:

    nanoc

Second and last, push the updated files in the `gh-pages` branch to Github:

    cd output
    git add .
    git commit
    git push

For more usage help see the [nanoc website](http://nanoc.ws/).
