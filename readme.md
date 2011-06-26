# Jackhq Mobile

A pure static html jquery mobile site.  The purpose of this site is to
demonstrate the capabilities of the jQueryMobile Framework as a web site
vs trying to be a native mobile application.

## Web vs Native

There are many frameworks in this new mobile battle providing solutions.
JQueryMobile is making its way into this space and is currently a beta 
release.  The focus of jQueryMobile is to provide a great web browsing
experience on as many mobile devices as possible.  It is not necessarily 
trying to bring a native like presence as much as it is trying to create
a responsive/progressive enhancement for the mobile user.

## Easy

jQueryMobile is Easy and focuses on using HTML 5 Data Attributes to
drive the style and navigation of the site.  The product of this focus, 
brings a very nice and accessible experience across a large amount of 
browsers.

## Head

When setting up your jQueryMobile site you may want to use the boiler
plate [jQueryBoilerPlate](http://jquerymobile.com/demos/1.0b1/#/demos/1.0b1/docs/pages/page-template.html)

There are some key things to remember:

* Set the Viewport

``` html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

* Insert your scripts between the jQuery and jQueryMobile script
  includes

``` html
<script src="http://code.jquery.com/jquery-1.6.1.min.js"></script>
<script> [Your Scripts Here] </script>
<script src="http://code.jquery.com/mobile/1.0b1/jquery.mobile-1.0b1.min.js"></script>
```

* Don't forget to link to the css

``` html
<link rel="stylesheet" href="http://code.jquery.com/mobile/1.0b1/jquery.mobile-1.0b1.min.css" />
```

## Page

Each mobile page is defined using a div tag with a data-role attribute
of "page".  The "id" attribute is the unique navigation element to move
from one page to another within one html document.  

``` html
<div id='home' data-role='page'>
...
</div>

...

<a href='#home'>Home</a>
```

## Header, Footer

## List Views

## Collapsible Content


