# Website Performance Optimization portfolio project

## Running Instructions 

Super easy to view both main pages in the project.

First page optimized is index.html, second page optimized is views/pizza.html.

Everything is basic html5, CSS and JS. Just download project and run both main pages to view.

## Project Solution
#### Part 1: Optimize PageSpeed Insights score for index.html

##### Step 1
**Problem**

Google Analytic js code and Google font code is blocking browser rendering path.

**Solution**

Move Google font to bottom of DOM to unblock rendering.

Save analytic code into renderAnalytic.js, move js file to bottom of DOM and add `async` attribute to unblock browser rendering path.

##### Step 2
**Problem**

Images are too large and must be compressed.

**Solution**

Compressed images to reduce memory and render images faster. 

#### Part 2: Optimize Frames per Second in pizza.html

## Steps To Achieve 60FPS In Pizza.html 
##### Step 1 
**Problem**

Browser generating random pizza one at a time then appending to DOM thus creating rendering delay.

**Solution** 

Declare document fragment(line 459 main.js), store all random pizza recipes generated into document fragment(line 460 main.js). Then append document fragment to DOM thus appending all recipes at once(line 470,471 main.js).

Use `document.getElementById` (line 412 main.js) and `document.getElementsByClassName`(line 437 main.js) Web API's to get a faster call from browser, 

##### Step 2
**Problem**

Pizzas in background that react to scrolling are not delivering 60fps.

**Solution**

Append generated pizzas in the background to the DOM all at once(line 571 main.js).

Abstract `phase`,`currentY`,`items` variables from for-loop(lines 525 - 529 main.js) to save computing power from browser.

Declare `lastYScroll` and `ticker`(lines 499, 500 main.js).

Create `onScroll` function(line 503 main.js) and bind to window event listener(line 546 main.js). 

Create `requestScroll` function(line 509 main.js) to use requestAnimationFrame when ticker equals false. Later redeclare ticker to true to not initiate requestAnimationFrame again until next scroll event. 

Calculate amount of pizzas needed for background based on window resolution. Delare variables `elem` and `left` outside for loop(lines 554, 555 main.js). Decalre var `windowHeight` to calculate window resolution(line 557 main.js). Declare var `neededPizzas` to calculate amount of pizzas needed for background based on `windowHeight` value(line 558 main.js). Replace satisfactory statment in for loop to (i < neededPizzas)(line 559 main.js). Set `left` var to (i%cols) * s (line 561 main.js). Set .basicLeft and style.left property for elem (lines 566, 567 main.js) and set to `left` variable.
##### Step 3
**Problem**

Pizzas next to recipes take to long to change size when user interacts with size navigation bar.

**Solution**

Abstract variables in for-loop(line 459 main.js) and declare all at once. This saves computing power for browser each time it runs the for loop thus optimizing browser rendering speed.

##### Step 5 (Optional)

Use the `use strict` tag in function definitons to enable strict mode thus helping to write more secure codes by preventing marking down a function with a bad syntax to execute or loading unused variables. (lines 344, 386, 519 main.js). 

Minify main.js and store into main-min.js reduce as much possible browser lag.

Increase site's performance by including hardware accelerated CSS in views/css/style.css. 
