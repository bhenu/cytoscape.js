# cytoscape.js



## Notice

Cytoscape.js has undergone major refactoring, including a change in name from the previous "Cytoscape Web" name.  **The code in the repository is currently unstable and should not be used by developers.**

Rest assured that we will continue development on the project to deliver a high-quality product.  You can still access the old Cytoscape Web 2 prerelease builds in the [Downloads section](https://github.com/cytoscape/cytoscape.js/downloads).  The documentation on the wiki can be used for those prerelease builds.

We are working hard to make Cytoscape.js better and in shape for a full release very soon.  Watch or star the project to keep updated on the project.




## Documentation

You can find the documentation on the [project website](http://cytoscape.github.com/cytoscape.js).  This readme is mostly for developers of Cytoscape.js.





## Acknowledgements

A big thanks goes out to Keith Wood for his jQuery SVG library, which is used
in Cytoscape Web's default SVG renderer implementation.  You can find out more
about his library at [his website](http://keith-wood.name/svg.html).

We would also like to thank Mark Gibson for his work on the jQuery color
library, which is used in our continuous mapper calculations.  You can find out
more about Mark's library at [his website](http://www.adaptavist.com/display/jQuery/Colour+Library).

We used Kevin Lindsey's SVG intersection library to calculate the positioning
of some objects, like edges.  You can find his library at [his website](http://www.kevlindev.com/gui/math/intersection).

We used Brandon Aaron's mouse wheel library for providing easy cross-browser
support for zooming with the mouse wheel in the SVG renderer.  You can find out
more about his library at [his website](http://brandonaaron.net).

Arbor was used in one of Cytoscape Web's included layouts.  We made some
modifications to the library, written by Samizdat Drafting Co., so that it
would work with multiple instances of Cytoscape Web and that it would work
on lesser browsers, like IE.  Information about this library can be found
at the [Arbor website](http://arborjs.org/) and on [GitHub](https://github.com/maxkfranz/arbor) where the original code was forked.





## Adding source files

When adding source (.js) files to the repository, there are several files that should be updated accordingly:

 * `Makefile` : Include the file in the build process so that the concatenated and minified files generated for distribution include the new file.

 * `src/debug/index.html` : Update the `<script>` tag list with the file so that the debug page can continue to be used to visually test the library.

 * `tests/index.html` : Update the list of JavaScript files that the testing framework considers to consistute the library.  Otherwise, the tests will almost certainly fail.




## Build dependencies

You need a number of executables installed on your system to successfully run
`make` to build the project.
	
Their paths are defined in `Makefile`, so you can revise the paths to these
executables and still run `make` successfully.  You should be able to run
`make` without modification on any well configured Unix-like machine, such as
Linux or Mac OS X---Mac needs XCode with command line tools installed to run
`make`.




## Build instructions

Run `make` in the console.  The targets are:

 * `all` : build everything (default)
 * `minify` : build the production minified JS
 * `zip` : minify and make a ZIP file for release
 * `clean` : deletes built files

A note to developers:

For `zip`, make sure to define `VERSION` in `Makefile` if you're making an
actual release ZIP.




## Tests

QUnit tests are found in the [tests directory](https://github.com/cytoscape/cytoscape.js/tree/master/tests).  The tests are automatically
run against different versions of jQuery.
