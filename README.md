heroku-buildpack-lessc
=========================

Heroku buildpack for a lessc binary.

This buildpack simply does a `npm install -g less` during its compile step, so you don't have to write any custom post-compile scripts to have a lessc binary on your dyno.


Usage
=====
To use, checkout the usage guide on https://github.com/ddollar/heroku-buildpack-multi then add this repo in your `.buildpacks`.

Example:
    
    $ cat .buildpacks
    https://github.com/heroku/heroku-buildpack-ruby
    https://github.com/jc4p/heroku-buildpack-lessc