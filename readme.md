# AutoCompleteJS

JavaScript autocomplete functionality for [Sublime Text][] with `method/function` signature (arguments) and `var` completion.

The package will keep an index of methods/functions seen in .js files doing a dumb parsing: it looks for `name = function(...)` and `name: function(...)` for opened folders. It does not evaluate objects(!).

Files are parsed only the first time these are seen and then will only re-parse a file if you save it (to keep the index up to date.)

As source for its index will look into:

-   All the js files of the current opened projects/folders. (this includes all the windows and scans for changes periodically in an optimized way, a file is only parsed in case of a cache miss)
-   If you open a js file that is outside the current project, it will scan the folder where this file resides.
-   Completion of methods/functions in unsaved files, and completion of `var`s for the current file are generated on the fly, with the incredible fast API of Sublime Text.

Will trigger its magic in js files and js scopes (eg in a script tag of an HTML file.)

This package is based in an idea from <http://www.eladyarkoni.com/2012/09/sublime-text-auto-complete-plugin.html> with performance improvements from  https://github.com/eladyarkoni/MySignaturePlugin/pull/7 and packed here for better openness

# Furter improvements

- Parse files with something like this: http://esprima.org/ instead of using RegExp


  [Sublime Text]: http://www.sublimetext.com/3
