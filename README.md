heroku-buildpack-lessc
=========================

Heroku buildpack for a lessc binary.

This buildpack simply does a `npm install -g less` during its compile step, so you don't have to write any custom post-compile scripts to have a lessc binary on your dyno.


Requirements
============
This buildpack uses `npm` directly, so you need to have it installed somehow for this to work. If you're just using this as an extra buildpack on-top of the nodejs buildpack (like in the first example below), you're all set. Else, read the usage section.

Usage
=====
To use, checkout the usage guide on https://github.com/ddollar/heroku-buildpack-multi then add this repo in your `.buildpacks`.

Simple example:
    
    $ cat .buildpacks
    https://github.com/heroku/heroku-buildpack-nodejs
    https://github.com/jc4p/heroku-buildpack-lessc

More complex example:

    $ cat .buildpacks
    https://github.com/heroku/heroku-buildpack-python
    https://github.com/heroku/heroku-buildpack-nodejs
    https://github.com/jc4p/heroku-buildpack-lessc

In this case, we have a Python (Flask) app that needs access to lessc, so in addition to using the regular python buildpack we have to also use the nodejs build pack to have `npm` be on the PATH.

Note that using the nodejs buildpack requires having a `package.json` file to detect what version of node to install, a sample one is listed in package.json.sample in this repo, and also below. Simply copy that file to your code's root folder and rename it to `package.json`

package.json.sample:

    {
      "engines": {
        "node": "0.12.x"
      }
    }