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

Using Dev Tools, I found that there was a forced synchronous layout being triggered by the slider for the random pizzas. Similar to the Browser Rendering Optimization course, I merged determineDx with changePizzaSizes.

I then decided to make an array for the random pizzas as I did for the moving ones. When making it so randomPizzas would be filled as new pizzas are generated in the beginning, I found that the for loop was calling for the div that holds the pizzas each time. I set that up before the loop instead.

Then I realized that the first two pizzas were not resizing. I noticed they were hard-coded into the page. So I changed the initial setup of randomPizzas from a new array to using document.getElementsByClassName("randomPizzaContainer").

Thanks to some pointers by the first Udacity code reviewer, I made some other improvements. Instead of guessing how many moving pizzas would be good for everyone, the number depends on the user's screen size. Also, I disabled backface visibility on them, which should help the moving pizzas reach 60 fps on more moderate hardware.

A second coach pointed out issues in my fetching of screensize, and so I did that. I also decided to take on the challenge of using translateX, which was kind of tricky. There were a couple other minor things I tried that were suggested.
