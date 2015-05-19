Cam's Pizzeria
==============

How to Use
----------

Open up pizza.html in your browser. The buttons at the top will jump you to that particular part of the page. While you scroll, the pizzas in the background will slide around with you.

The pizzas come in a whole lot of varieties, all generated at random. At the "Our Pizzas" section, you'll find all these kinds. Adjust the slider to the different sizes, and the images for those pizzas will adjust in size as well.


Fixing the Moving Pizzas
------------------------

The first thing I did was move the phase calculations out of the for loop in updatePositions, as that was causing a forced synchronous layout.

Next, I reduced the number of pizzas on screen to 40, feeling 200 was waaay more than anyone would be seeing. A thanks to Mark for [the tip](https://github.com/udacity/fend-office-hours/tree/master/Web%20Optimization/Effective%20Optimizations%20for%2060%20FPS).

I then moved getting all the array elements for the moving pizzas outside of updatePositions. I created an array called movingPizzas near the top of the file and, in the loop that creates each of the pizzas, I had it add each element to movingPizzas while it was at it. I also decided to reduce the number of pizzas further, tweaking the column amount down to 6 and the total number to 24.


Fixing the Random Pizzas
------------------------


