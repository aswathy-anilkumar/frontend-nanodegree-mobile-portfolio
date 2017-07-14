## Website Performance Optimization portfolio project

Your challenge, if you wish to accept it (and we sure hope you will), is to optimize this online portfolio for speed! In particular, optimize the critical rendering path and make this page render as quickly as possible by applying the techniques you've picked up in the [Critical Rendering Path course](https://www.udacity.com/course/ud884).

To get started, check out the repository and inspect the code.

### Getting started

#### Part 1: Optimize PageSpeed Insights score for index.html

Some useful tips to help you get started:
1. Check out the repository
1. To inspect the site on your phone, you can run a local server
  ```bash
  $> cd /path/to/your-project-folder
  $> python -m SimpleHTTPServer 8080
  ```
1. Open a browser and visit localhost:8080
1. Download and install [ngrok](https://ngrok.com/) to the top-level of your project directory to make your local server accessible remotely.
  ``` bash
  $> cd /path/to/your-project-folder
  $> ./ngrok http 8080
  ```
1. Copy the public URL ngrok gives you and try running it through PageSpeed Insights! Optional: [More on integrating ngrok, Grunt and PageSpeed.](http://www.jamescryer.com/2014/06/12/grunt-pagespeed-and-ngrok-locally-testing/)

#### Part 2: Optimize Frames per Second in pizza.html

To optimize views/pizza.html, you will need to modify views/js/main.js until your frames per second rate is 60 fps or higher.

- For updatePosition() function, changed *querySelectorAll* to *getElementsByClassName* . Moved the variable calling  *layout property*  scrollTop out of for-loop since it's retriggering a layout change.
- Created new variable *top* to cache **document.body.scrollTop**. Then added an array since *Math.sin((document.body.scrollTop / 1250) + (i % 5))* .
-  Used the array to optimize the *for-loop* to call these values when triggering the style changes to the background pizzas.
- For *changePizzaSizes()* function, added new variable *randomPizza* to replace document.querySelectorAll(".randomPizzaContainer") and removed *dx* and     newwidth  variables out of the for loop since both are not needed. Added switch cases to change pizza pic by percentage instead of pixels.


* <a href="http://getbootstrap.com/css/">Bootstrap's CSS Classes</a>
* <a href="http://getbootstrap.com/components/">Bootstrap's Components</a>
