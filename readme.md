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

If you want more compact buttons then wrap them with a div with
an attribute of data-inline and set it to true.

``` html
<div data-inline="true">
	<a href="index.html" data-role="button">Cancel</a>
	<a href="index.html" data-role="button" data-theme="b">Save</a>
</div>
```

### Grouping buttons

You can group buttons in a horizontal group.

``` html
<div data-role='controlgroup'>
  <a href='#'>Button1</a>
  <a href='#'>Button2</a>
</div>
```

### Button Themes

You can control the color of your buttons by using the
data-theme attribute.

``` html
<a href='#' data-theme='e'>Button</a>
```

## List Views

List views is by far the most powerful feature of the 
jQuery mobile platform.  It makes it very simple to 
add and organize your list of data.

``` html
<ul data-role='listview'>
  ...
</ul>
```

When placing links inside a listview ul, jQueryMobile 
automatically makes the entire listitem clickable.

If you add two link elements in one li of the listview,
jQueryMobile will create a split button, where the left
side of the li will click to the first link element and the
right side will click to the second element.

You can also build nested lists.

You can add a count bubble to your items.

``` html
<ul data-role='listview'>
  <li><a href='#'>Item 1</a><span class='ui-li-count'>3</span></li>
</ul>
```

You can add supplemental information to your item using the ui-li-aside
class.

``` html
<ul data-role='listview'>
  <li><a href='#'>Item 1</a><span class='ui-li-aside'>Author</span></li>
</ul>
```

Thumbnails are automatically reconized as the first image in the li
element and resized to 80x80 px.

Icons can be added as well, as span elements.

If you need to dynamically add items to lists, simply call the
listview('refresh') method.

### List Divider

List Divider will create a section header as a list line item.

### Search Filter

Simply set data-filter attribute on the ul element to true and you 
have a searchable list.

``` html
<ul data-role='listview' data-filter='true'>
 ...
</ul>
```

### Inset List

You can switch your listview to an inset view vs the list wrapping
from end to end of your screens width.

``` html
<ul data-role='listview' data-inset='true'>
...
</ul>
```

### Summary 

If you do not like any of the features of the list view, it is pretty
easy to create your own custom list, and if you need momentum scrolling
it is pretty easy to add a jquery plugin to handle this as well.

But the Listview component is a great solution to provide quick
functionality across a host of devices.


## Collapsible Content

Collapsible Content allows you to hide and show sections of your page.

This is great to allow your users to not have to scroll long sections 
of content.  

* One thing to look out for, is the usage of paragraph tags inside
collapsible content or list views, jQueryMobile will automatically
concantenate the length.

``` html
<div data-role='callapsible'>
  <h3>Header</h3>
  <div>Hidden or Shown text based on the users click</div>
</div>
```

The h3 tag text is displayed at all times, the rest is hidden.

The default is to show the collapsible content, but you can override 
this default by using the data-collapsed attribute and set it to true.

### Collapsible sets

``` html
<div data-role='collapsible-set'>
  <div data-role='collapsible'>
    <h3>XXXX</h3>
    <div>Data</div>
  </div>
</div>
```

## Themes

The themes are designed by using the letters of the alphabet.  You can
have up to 26 themes.  jQueryMobile comes with 5 built in.  These allow
you to change the view of many items.  By setting the data-theme attribute
and providing it a letter, will change the color and view of the theme.

It is real easiy to creat your own themes - check out
[jQueryMobile](http://jquerymobile.com)

---

## Please see index.html to see most of these features in action.

# Contribution

If you would like to contribute, just fork this repo and submit a pull
request.

# Bugs

Please document any issues you find with this markup to the issues tab
in Github, we will respond quickly.

# Thanks

Thanks to the creators of jQuery, jQueryUI and jQueryMobile!

Thank you to everyone who takes the time to read this and comment on it.


