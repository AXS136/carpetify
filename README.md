# carpetify

A [browserify](http://github.com/substack/node-browserify) transform for the [istanbul](https://github.com/gotwarlost/istanbul) code coverage tool using the [nyc](https://github.com/istanbuljs/nyc) CLI.

This is a fork of the original [browserify-istanbul](https://github.com/devongovett/browserify-istanbul).

## Installing

    npm install --save-dev carpetify

## Usage

This library should be used as a transform to your browserify bundle -- it will
instrument the code in the bundle that doesn't match the ignore filter.

Please see the [browserify](https://github.com/substack/node-browserify) repo
for full instructions on how to use browserify plugins.

You can pass in several configuration options to the plugin:
* `defaultIgnore:boolean` - use the default ignores or not
* `ignore:array(string)` - an array of strings to pass to minimatch to ignore files.
* `stripBasePath:boolean` - by default the full path to the file on your disk will be provided. This can be a problem if you want to use the default ignores but your parent directory contains one of the ignores. This will strip off the leading directories, allowing coverage to work

This will instrument all the code and generate a coverage report, attached to the
window object in the browser. You'll likely need another tool to deal with this,
you might want to check out:

* [tape-istanbul](https://github.com/bendrucker/tape-istanbul) - writes coverage data to disk
* [tape-coverage](https://github.com/toddself/tape-coverage) - uses tape-istanbul & tape-run to automate report generation


## License

MIT
