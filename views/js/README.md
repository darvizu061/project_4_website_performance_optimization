## Steps To Achieve 60FPS In Pizza.html 
##### Step 1 
**Problem**

Browser generating random pizza one at a time then appending to DOM thus creating rendering delay.

**Solution** 

Declare document fragment(line 473 main.js), store all random pizza recipes generated into document fragment(line 474 main.js). Then append document fragment to DOM thus appending all recipes at once. 

##### Step 2
**Problem**

Pizzas in background that react to scrolling are not delivering 60fps.

**Solution**

Append generated pizzas in the background to the DOM all at once(line 576 main.js).

Abstract `phase`,`currentY`,`items` variables from for-loop(line 542 main.js) to save computing power from browser.

Declare `lastYScroll` and `ticker`(line 518, 519 main.js).

Create `onScroll` function(line 517 main.js) and bind to window event listener(line 558 main.js). 

Create `requestScroll` function(line 523 main.js) to use requestAnimationFrame when ticker equals false. Later redeclare ticker to true to not initiate requestAnimationFrame again until next scroll event.  

##### Step 3
**Problem**

Pizzas next to recipes take to long to change size when user interacts with size navigation bar.

**Solution**

Abstract variables in for-loop(line 459 main.js) and declare all at once. This saves computing power for browser each time it runs the for loop thus optimizing browser rendering speed.