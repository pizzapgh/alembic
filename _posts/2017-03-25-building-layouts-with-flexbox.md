---
title: Building Layouts With Flexbox
category: General
excerpt: To get familiar with flexbox, I decided re-create layouts using flexbox...
---

## Tutorial

Lets build this layout using flexbox

![alt text](/assets/chocolate-moon-shine-layout-1.png "fart")

## First Step

Create a div with a wrapper class. This will be your container for the rest of your content.

~~~~~~~~~~~~~~~~~~~~~~~~~

<section class="wrapper">

</section>

~~~~~~~~~~~~~~~~~~~~~~~~~

Set a width of 70% and center it using margin: auto and add the following css.

~~~~~~~~~~~~~~~~~~~~~~~~~

.wrapper{
  width: 70%;
  margin: 3rem auto;
  text-align: center;
  background: white;
  padding: 2rem 0;
  border: 1px solid black;
}

~~~~~~~~~~~~~~~~~~~~~~~~~

![alt text](/assets/chocolate-moon-shine-layout-step-1.png "fart")


## Second Step
Add a div with the class of inner-wrap div and inside your inner-wrap add 3 divs with a class of col.
~~~~~~~~~~~~~~~~~~~~~~~~~

<section class="wrapper">
  <h2>Our Products</h2>

   <div class="inner-wrap">
     <div class="col">
       <img src="http://placehold.it/350x350">
       <h3>Moonshine Bars</h3>
     </div>

     <div class="col">
       <img src="http://placehold.it/350x350">
       <h3>Moonshine Bars</h3>
     </div>

     <div class="col">
       <img src="http://placehold.it/350x350">
       <h3>Moonshine Bars</h3>
     </div>
  </div>

</section>

~~~~~~~~~~~~~~~~~~~~~~~~~

Add a 80% width on your col images with 100% border-radius to make the placeholder images into circles.
So right now your columns should be stacked. To inline the divs into a row, add display flex on the inner-wrap class. Next add flex-basis of 32% on your divs with the class of col.

~~~~~~~~~~~~~~~~~~~~~~~~~

.wrapper{
  width: 70%;
  margin: 3rem auto;
  text-align: center;
  background: white;
  padding: 2rem 0;
  border: 1px solid black;
}
.col img{
  width: 80%;
  border-radius: 100%;
}
.inner-wrap{
  display: flex;
  border: 1px solid blue;
}
.col{
  flex-basis: 32%;
  height: auto;
  border: 1px solid green;
}

~~~~~~~~~~~~~~~~~~~~~~~~~
![alt text](/assets/chocolate-moon-shine-layout-step-2.png "fart")

To add margin in between the columns we can use the justify-content property by adding space-between. This will spread out the columns in the parent container using up the rest of the space given.

~~~~~~~~~~~~~~~~~~~~~~~~~

.inner-wrap{
  display: flex;
  justify-content: space-between;
  border: 1px solid blue;
}


~~~~~~~~~~~~~~~~~~~~~~~~~

![alt text](/assets/chocolate-moon-shine-layout-step-3.png "fart")

To make the layout responsive, add the following css.
Setting flex-direction to column will stack the cols on top of each other.

~~~~~~~~~~~~~~~~~~~~~~~~~

@media (max-width: 768px){
  .inner-wrap{
    flex-direction: column;
  }
}


~~~~~~~~~~~~~~~~~~~~~~~~~


![alt text](/assets/chocolate-moon-shine-layout-step-4.png "fart")

## Codepen

View code [http://codepen.io/drunktuts/pen/mWKNeY?editors=1100](http://codepen.io/drunktuts/pen/mWKNeY?editors=1100)

## Summary

Flexbox allows you to control your layouts without having to using inline or floats. No longer do we have to use annoying hacks like clearfix or overflow hidden to prevent collapsing. Flexbox provides us with helpful properties like justify-content space-between allowing us to add margins to our columns. Learn more about flexbox. [Learn more](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
