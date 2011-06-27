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

Creating a header and footer are also semantic using the data-role
attribute.

``` html
<div data-role='page'>
  <div data-role='header'>
    <h1>Header Info Here</h1>
  </div>
  ...
  <div data-role='footer'>
    <p>Footer Info here</p>
  </div>
</div>
```

You can control the theme of the header and footer using the data-theme
attribute.

``` html
<div data-role='header' data-theme='b'>
  ...
</div>
```

### Fixed Screen Toolbars

You can create fixed headers and footers by setting the
data-position to 'fixed'

This provides an interesting effect, basically when the user scrolls
up or down, the header or footer disappears, when the scrolling is 
completed, they re-appear in their fixed position.  In the alpha
releases we had trouble using footers on various devices and layout
changes.  We abandoned fixed footers and just use the footers at the
bottom as in a natural web page.  

``` html
<div data-role='footer' data-position='fixed'>
 ...
</div>
```

### Fullscreen Toolbars

You can create fullscreen headers and footers by setting
the data-position attribute to 'fullscreen'

This has a similar effect as the fixed, except the bar only appears
after the user clicks or taps the screen.

``` html
<div data-role='footer' data-position='fullscreen'>
  ...
</div>
```

### Navigation Buttons in Headers 

When you place a link element in the header toolbar, jQueryMobile
will automatically render it as a button, and put it to the left of the
title.  The second link will be placed at the right of the title.

``` html
<div data-role='header'>
  <a href='#'>Left</a>
  <h1>Title</h1>
  <a href='#'>Right</a>
</div>
```

You can force the position of a button by using the class attribute of
the link elelment.

``` html
<div data-role='header'>
  <h1>Title</h1>
  <a href='#' class='ui-btn-right'>Right</a>
</div>
```

### Adding the Back Button to a page

The back button is automatically disabled by default, you can re-enable
on a per page level by adding the "data-add-back-btn" attribute and
setting it to true on the page element.

``` html
<div data-role='page' data-add-back-btn="true">
  ...
</div>
```

You can also define the text of the back button on the page element.

``` html
<div data-role='page' data-add-back-btn="true" data-back-btn-text="previous">
  ...
</div>
```
## Navigation Bars

It is equally as easy to setup navigation bars in jQueryMobile.  With
the declaritive style you simply specify you navbar via the data-role
attribute.

Inside the navbar you want to add an unordered list element with line
item elements.  These will automatically paint inline and divide the
width of the parent into button sections.

Navbars can also specify a particular button as active by adding a
ui-btn-active class to the the particular element.

``` html
<div data-role='navbar'>
  <ul>
    <li class='ui-btn-active'><a href='#'>Menu1</a></li>
    <li><a href='#'>Menu2</a></li>  
  </ul>
</div>

```

You can also add icons and position icons to the buttons in the 
navbar, just like you can with any button.

``` html
<a href='#' data-icon='home' data-iconpos='top'>Home</a>
```

For more information see: [jQuery NavBar](http://jquerymobile.com/demos/1.0b1/#/demos/1.0b1/docs/toolbars/docs-navbar.html)

## Buttons

Any submit, button, reset, image will automatically default to the
button css presentation.  When using link elements in headers and
footers, they will also default to the button style.  But when it the
link is outside of the header or footer and in the content container,
you must add the data-button attribute to the element.

``` html
<a href='#' data-button='true'>My Custom Button</a>
```


## List Views

## Collapsible Content


