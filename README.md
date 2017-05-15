# Website performance Optimization

### Part one: Improve index.html to get higher pageSpeed score
#### CSS/Font
- Inline **style.css** as it is very small
- Remove font reference, as it only affect four words
- Add media query **media="print"** to the reference of **ptint.css**, as it only affects print and shouldn't block initial rendering

#### JS
- Add **async** attribute to reference of **analytics.js**. As function like analytics isn't required at initial load and shouldn't block paring

#### HTML
- Remove redundant code like notes, white spaces etc.

#### Picture optimization
- The size of image files is not big, so not much to improve

#### Cache / gzip
- Will consider these two when use web server like Nginx, Apache etc.

### Part two: Improve pizza site to achieve 60 fps
- line 503, **scrollTop** requires to run layout and will trigger the FSL. Move it outside the loop
- Remove useless but complex function **determinDx**. Improve function *changePizzaSizes* to avoid FSL
- Line484, place handler inside of **requestAnimationFrame()** to avoid frame lost
- line 490, move **document.body.scrollTop / 1250** outside of the loop to avoid avoid FSL
- Replace **querySelect()** with more efficient functions like **getElementsByClassName()** **getElementById()** etc.
- Place variable declaration outside the for loop to avoid create variable repeatedly
- Instead of using 200 moving pizza, dynamically calculate the pizza number that need to be displayed base on current viewport's height
- Compress pizzeria.jpg to reduce the size to 310KB
### Lisense
- This is a Udacity practice project