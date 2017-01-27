## Web Optimization Project

Sixth project from the Front-End Web Developer Nanodegree in <a href="https://www.udacity.com" target="_blank">Udacity</a>:
<br>
- Part 1: Optimize PageSpeed Insights score for `index.html`
- Part 2: Optimize Frames per Second in `pizza.html` and `main.js`

### To run the application

[Project Repo](https://github.com/markchen555/Website-Optimization-Project)

Fork a copy from my github or download the repository on your computer, unzip it and open `index.html` in your browser to see the working tests. See detail for part 1 in `../index.html`. See detail for part 2 in `../views/js/main.js

---

### Optimization

####Part 1: Optimize PageSpeed Insights score for `index.html`

I used python simplehttpserver to host local website then used `ngrok` to create public website to run test on Google PageSpeed score of `index.html`

To increase the score to at least 90, I made the following changes:

- Compress size and quality of all the images inside img file with `gulp`.
- Inlined CSS in `style.css` to prevent render blocking.
- Inlined CSS in `print.css` to prevent render blocking. 
- Moved inline Google Analytics script and related script `http://www.google-analytics.com/analytics.js` to just above closing body tag and added async attribute. 
- Implemented script to load Google font after initial painting of page
- Created .htaccess file and set expiration dates for static resources
- Added catch control meta in the header

####Part 2: Optimize Frames per Second in `pizza.html` and `main.js`

To reach a frame rate of 60 fps when scrolling, I made the following changes:

- Created `scroll` variable `(var scroll = (document.body.scrollTop / 1250))`
- Decreased number of pizzas created on page from 200 to 30
To make time to resize pizzas less than 5ms, I made the following changes:

- In function resizePizzas replaced `querySelectorAll` method with `getElementsByClassName`
- In function `changePizzaSizes`, factor out `.randomPizzaContainer` and replaced `querySelectorAll` method with `getElementsByClassName`
- In the same function, moved variable declarations for `dx` and `newwidth` outside `for` loop
- In function updatePosition replaced `querySelectorAll` method with `getElementsByClassName`
- Declaring the elem variable in for loop to prevent it been created every time called.
- In elem for loop replaced `querySelector` method with `getElementsById`

---

### Udacity's instructions

In this project you will optimize a provided website with a number of optimization and performance-related issues so that it achieves a target PageSpeed score and runs at 60 frames per second.

- Review our course on Website Performance Optimization using Google PageSpeed.
- Download the required project assets.
- Use Chrome Developer Tools to review the current state of various pages within the application and identify areas for improvement.
- Review the code powering the website and identify areas where you believe modifications are warranted.
- Iteratively make changes and test those changes using the tools available to you to determine if they are a performance gain or loss.


---

### Reference

[Ngrok Local Web Server](https://ngrok.com/docs)
[Gulp.js](http://gulpjs.com/)
[Grunt.js](http://gruntjs.com/getting-started)
[Google PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/)

---

### License

The project is licensed under the [MYC license](license.txt).
# Website-Optimization-Project
