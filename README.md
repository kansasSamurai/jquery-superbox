# jquery-superbox
[INACTIVE] jQuery Superbox! is a script which allows you display windows with the lightbox effect.

https://bpier.re/projects/jquery_superbox/

jQuery SuperBox! is deprecated and won’t be updated.

I recommend to use an alternative like Magnific Popup for any new project.
If you are interested in maintaining jQuery SuperBox!, you can fork the latest version on GitHub.
Introduction

jQuery Superbox! is a script which allows you display windows with the lightbox effect.

This script is a plugin for jQuery (1.3.x).

Why create a new script of this kind, when many exist already?

Accessibility. only the rel attribute is used to launch the script. The href attribute is therefore coherent: it targets the address of a picture, of a page, or an element identifier (anchor).
Extensibility. Superbox doesn't set any style, everything is easily and entirely CSS stylable.
The MIT license. this license allows you to use, duplicate, modify, publish, distribute, merge, sell and even change the script license. Your only obligation is to keep the script's author name.
It's fun.
jQuery Superbox! can display pictures, pictures galleries, external pages, a page element or even AJAX loaded content.

Download
The minified version of Superbox is 2kb when using GZip compressing, 5.4kb otherwise.

Donwload jQuery Superbox! 0.9.1 (zip)

Contribute
You want to participate? Don't hesitate to visit the Bittbucket project webpage; there you can report bugs, suggest improvements and contribute to the code: http://bitbucket.org/bpierre/jquery-superbox/

Getting started
To install this script, you must include on your page jQuery, as well as the files jquery.superbox-min.js (minified version) and jquery.superbox.css:

<link rel="stylesheet" href="jquery.superbox.css" type="text/css" media="all" />
<script type="text/javascript" src="jquery-min.js"></script>
<script type="text/javascript" src="jquery.superbox-min.js"></script>
By default, the superbox is generated from the rel attribute of a link. It must contain the word superbox, followed by the display mode in square brackets: rel="superbox[display_mode]".

The code name will eventually be associated to an id and one or several class (CSS syntax) which will be applied to the generated window: rel="superbox[type#my_id.my_class]".

The parameters specific to the display mode will then be put behind, in square brackets.

The windows is placed in position:fixed, except if its height exceeds the display area. In that case, it will go in position:absolute, which will allow to see the whole zone using the browser's scroll bars.

To activate jQuery Superbox!, the $.superbox() method must be executed at the page's loading:

$(function(){
	$.superbox();
});
Some parameters can be defined; all are optional. The default values are as follow:

$.superbox.settings = {
	boxId: "superbox", // Id attribute of the "superbox" element
	boxClasses: "", // Class of the "superbox" element
	overlayOpacity: .8, // Background opaqueness
	boxWidth: "600", // Default width of the box
	boxHeight: "400", // Default height of the box
	loadTxt: "Loading...", // Loading text
	closeTxt: "Close", // "Close" button text
	prevTxt: "Previous", // "Previous" button text
	nextTxt: "Next" // "Next" button text
};
Picture mode
Displays a box containing a picture.

Demo
Superbox picture (auto dimensions)

Superbox picture (defined width)

Superbox picture (defined height)

Use
By default, the dimensions take those of the picture (it's possible to add a padding with css):

<a href="http://example.com/picture.png" rel="superbox[image]">SuperBox</a>
But it is also possible to specify the dimensions :

<a href="http://example.com/picture.png" rel="superbox[image][500x200]">SuperBox</a>
Width only:

<a href="http://example.com/picture.png" rel="superbox[image][500x]">SuperBox</a>
Height only:

<a href="http://example.com/picture.png" rel="superbox[image][x200]">SuperBox</a>
If the picture's height exceeds the box's height, the specified height is ignored.

If a title attribute exists on the link, it will be transfered over to the picture. If not, it's the text of this link which will be taken for the title attribute of the picture.

Gallery mode
Displays a picture gallery. It is possible to navigate using the buttons or the arrow keys.

Demo
Auto size:
  

Defined dimensions:
  

Use
The second parameter will be the gallery's name. All links wearing this name will be part of the same galley.
By default, the dimensions take those of the picture (it's possible to add a padding with css):

<a href="http://example.com/picture.png" rel="superbox[gallery][my_gallery]">SuperBox</a>
But it is also possible to specify the dimensions:

<a href="http://example.com/picture.png" rel="superbox[gallery][my_gallery][500x200]">SuperBox</a>
Width only:

<a href="http://example.com/picture.png" rel="superbox[gallery][my_gallery][500x]">SuperBox</a>
Height only:

<a href="http://example.com/picture.png" rel="superbox[gallery][my_gallery][x200]">SuperBox</a>
If the picture's height exceeds the box's height, the specified height is ignored.

Iframe mode
Generates a box containing an iframe.

Demo
Iframe Superbox (default dimensions)

Iframe Superbox (defined dimensions)

Use
<a href="http://example.com/" rel="superbox[iframe][700x500]">SuperBox</a>
Content mode
Generates a box containing an element of the page.

The link will be external, and will point to an element of the page using its id attribute.

This element will be copied to appear in Superbox.

Demo
SuperBox element

SuperBox element (dimensions)

Use
<a href="#box-content" rel="superbox[content]">SuperBox</a>
AJAX mode
Generates a box containing an HTML fragment loaded with AJAX.

The link point to a complete HTML document (non-intrusive version), while the AJAX URL takes place in second parameter.

Démonstration
AJAX SuperBox

AJAX SuperBox (dimensions)

Utilisation
<a href="#box-content" rel="superbox[content]">SuperBox</a>
