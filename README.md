Website Performance Optimization portfolio project
==================================================

How to Use
----------

Just open up index.html in your browser.

The pizza.html optimizations can be reached at the bottom, at "Cam's Pizzeria". A README on the optimizations made on that can be found in the views folder.


Fixing Up index.html
--------------------

The first thing that PageSpeed Insights pointed out was that the images could use some compressing. I made a much smaller version of pizzeria.jpg (putting this version in the img folder) and then compressed all of the images using Trimage.

The next thing up was eliminating render-blocking CSS and JavaScript. I set print.css line with media="print" to only be used when trying to print. I moved all the JavaScript to the bottom of the page, making the one .js file that wasn't already set to async to be set to it. I also made the inline JavaScript use onload, so it waits for the page to be built since it isn't important to the page itself. I got help from that thanks to Mozilla's documentation [here](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onload).

I also removed the Google font and inlined the single CSS file that was being applied, aiming for the best score I could get.

The mobile side seemed to be as good as I could get it. I checked the other tab, and it suggested that I shrink pizzeria.jpg further. I did that, and then I moved onto working on pizza.html.
