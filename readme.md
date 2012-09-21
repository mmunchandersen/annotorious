This is an effort to port the "yuma.js":http://yuma-js.github.com image annotation toolkit to JavaScript, improving things as we go along. Any help appreciated! I'm putting up live demos of the intermediate state as we progress:

http://rsimon.github.com/yuma2

## Using

To make images on your Website annotatable with this library, follow these steps:

__Include the library JavaScript__ file in the &lt;head&gt; of your HTML page

    <head>
      ...
      <script type="text/javascript" src="yuma2.min.js"></script>
      ...
    </head>

__Include the library CSS stylesheet__ in the &lt;head&gt; of your HTML page

    <head>
      ...
      <link rel="stylesheet" type="text/css" href="css/yuma2.css" />
      <script type="text/javascript" src="yuma2.min.js"></script>
      ...
    </head>  

__Use the library JavaScript API__ to attach annotation functionality to images on your page.

    <head>
      ...
      <script type="text/javascript">
        new ImageAnnotator('annotateme');
      </script>
    </head>

    <body>
      ...
      <img id="annotateme" src="myimage.jpg">
      ...
    </body>

That's it. (Note: it's going to be even easier in the future as we're going to use CSS-class based selection...)

## Developing

We're using Google's [Closure Tools](http://developers.google.com/closure/). I recommend using the [plovr](http://plovr.com/) build tool to get started quickly. (Plovr requires Java to be installed on your system.)

* Run ``java -jar plovr/plovr.jar serve standalone.json`` in the working directory 
* Open ``index.html`` in your browser - and code away
* To build the minified JavaScript, run ``java -jar plovr/plovr.jar build standalone.json > yuma2.min.js`` (replacing 'yuma2.min.js' with a file name of your choice)
* Note: the version of plovr I included in this repository is the February 2012 release ([plovr-4b3caf2b7d84.jar](http://code.google.com/p/plovr/downloads/detail?name=plovr-4b3caf2b7d84.jar&can=2)).

## Todos (almost in order of priority...)

* Delete/edit of annotations
* Change the way activation works: activation no longer via JavaScript ("new ImageAnnotator(id)") but via a CSS class ("&lt;img class='annotatable' ... /&gt;")
* Create an OKFN Annotator Plugin wrapper (plus a custom JS build for the plugin)
* Make selection move/resizable after it is created
* Attach storage according to "OKFN Annotator Store":http://github.com/okfn/annotator/wiki/Storage protocol
* OpenLayers and/or Seadragon AJAX support
* Implement POINT and POLYGON shape geometries
* Add support for the "toponym selection tool":http://github.com/rsimon/toponymotator
* *Find a decent name for this tool!*
* ~~Popup annotation text bubble~~ *DONE* (but needs some style)
* ~~Popup annotation create/edit form~~ *DONE* (but needs some style)
* ~~Clean up namespacing (it's a bit messy after the last refactoring)~~ *DONE*
* ~~Central event bus/event broker to keep code tidy~~ *DONE*
* ~~Custom mouseover/mouseout events for annotation shapes~~ *DONE*

## License

This work is licensed under the "GNU General Public License v3.0":http://www.gnu.org/licenses/gpl.html.
