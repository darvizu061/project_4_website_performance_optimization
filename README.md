## Website Performance Optimization portfolio project
#### Part 1: Optimize PageSpeed Insights score for index.html

##### Step 1
**Problem**

Google Analytic js code and google font code is blocking browser rendering path.

**Solution**

Move google font to bottom of DOM to unblock rendering.

Save analytic code into renderAnalytic.js, move js file to bottom of DOM and add `async` attribute to unblock browser rendering path.

##### Step 2
**Problem**

Images are to large and must be compressed.

**Solution**

Compressed images to reduce memory and render images faster. 

#### Part 2: Optimize Frames per Second in pizza.html

Continued in views/js/README.md 
