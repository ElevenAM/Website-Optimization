# Website-Optimzation
elevenam.github.io/website-optimization

Optimizing a Website

pizza.html originally had a Google PageSpeed score of 35/100 for mobile and 47/100 for desktop. After making changes, the page now has a speed of 97/100 for mobile and 94/100 for Desktop.

Improving Pagespeed Insights

A page loads by rendering the instructions given to it by a combination of its HTML/ CSS and Javascript components. Along the way, it will have to make requests from the server for pieces it needs and may even have to stop and wait for pieces to come before continuing to render the page. The number of server requests is called the "Critical Rendering Path Length" and steps that hold up the page render are called "Render Blocking".

As such, to improve a page's speed as much as possible, we must keep the Critical Rendering Path as short as possible while eliminating as many "render blocking" elements as possible.

What was done
1. Created async script requests to avoid render blocking
2. Reorganized index.html to minimize the Critical Rendering Path
3. Inlined CSS into the HTML so that we don't need to make as many server requests for the CSS
4. Used Javascript to load resources after the DOM has been loaded
5. Reduce file size of images/ CSS by compressing and minifying where possible
6. Create a "combined" javascript document to load the CSS in a single trip


Improving Javascript

The page originally had two Javascript functions that weren't functioning as fast as they could have been. There were pizzas that moved in the background as you scrolled and a slider that changed the size of the pizzas displayed.

Pizza Scrolling

To improve the FPS of the page while scrolling, we had to reduce the amount of times that the DOM was manipulated. To achieve this, I simply minimized the number of pizzas being manipulated. We now acquired the dimensions of the screen and made sure that rather than 200 pizzas being moved, we only moved the pizzas currently being displayed on the screen. From there, minor manipulations to the Javascript functions were made like using the translateX style to move the element to minimize DOM manipulation.

Changing Pizza Size

Originally, the pizza size would be changed when a slider's position was moved. Upon moving, it would engage the changePizzaSizes() function and loop through all of the pizzas. There were a number of variables/ function calls that were being created/run every time the loop was run when they didn't need to be. I modified the function so that variables and functions were only created/ run as they needed to be.

Resources
bahalps.github.io - Showed me how to create a combined.js file to launch CSS. Also helped me figure out how to start improving my pizza scrolling/ how to use translateX to reduce DOM manipulations

Udacity Code Reviewer -
Commented on my code and gave me pointers on what I might look into doing to improve function changePizzaSizes()

Google Developers CSS Optimization Guide - https://developers.google.com/speed/docs/insights/OptimizeCSSDelivery#example 