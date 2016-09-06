#Intro to HTML and CSS (28 Mar 2016)

folder structure - HTML (Document Object Model), stylesheet

Elements are made up of tags (opening and closing), with optional attributes (with its associated values) and content

class -> .classname

ID -> #IDname

use < div > for creating “boxes”

[Content sectioning](https://developer.mozilla.org/en-US/docs/Web/HTML/Element#Content_sectioning)

[CSS selectors](https://css-tricks.com/how-css-selectors-work/)

[CSS style attributes](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)

[normalize.css](http://necolas.github.io/normalize.css/) to normalise css across different web browsers' default settings

[default CSS styles used by browsers](https://www.w3.org/TR/CSS21/sample.html)

the box model - padding, border, margin

To include padding + border for border size to set width, height etc (will set box size to be a fixed no matter what the padding and border is. Margin not included) :-

	* {
		-webkit-box-sizing: border-box;
		-moz-box-sizing: border-box;
		-ms-box-sizing: border-box;
		box-sizing: border-box;
	}

A flex container expands items to fill available free space, or shrinks them to prevent overflow.

	.container {
		display: flex; <!--prevents overflow-->
		flex-wrap: wrap; <!--allows wrappinn to next row instead of resizing elements-->
	}

[Guide to flex box](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

[To verify HTML](http://validator.w3.org/#validate_by_input)

[To verify CSS](http://jigsaw.w3.org/css-validator/#validate_by_input)

[CSS frameworks](https://en.wikipedia.org/wiki/CSS_frameworks)

setting a max width of 960px is a good practice so that the website will look good on various screen sizes

12 column grid system is the best:-

	.row of 100%
		.row {
			display: flex;
			flex-wrap: wrap;
		}
	.col of 1/12 to 12/12
		col-1, col-2, ... , col-12
			.col-3 {
				width: 25%;
			}

use negative space for readability :- padding and margin

use "overflow: auto" for long text to be scrollable

media queries - change css properties depending on device, screen size and color for responsive design
device emulation:-

	@media only screen and (max-width: 500px) {
		p {
			display: none;
		}
	}

use normalize.css to have same look across browsers:-

	<head>
		<link rel="stylesheet" src="//normallze-css.google.com/svn/trunk/normalize.css">
	</head>


place it images:-

	<img src="http://placehold.it/960x350">
	<img src="http://placekitten.com/200/300">

google fonts:

	* {
		font-family: 'Indie Flower', cursive;
	}

CSS frameworks (use the class names in the framework and not your own):-
 * [Bootstrap](http://getbootstrap.com/)
 * [Foundation](http://foundation.zurb.com/)
 * [Yaml](http://www.yaml.de/)
 * [960 Grid](http://960.gs/)
 * [Suzy](http://susy.oddbird.net/)

To include the minified CSS and JS files:-

	<link rel="stylesheet" href="css/bootstrap.min.css">
	<script src="js/bootstrap.min.js"></script>

You can manually minify your CSS using a site like http://cssminifier.com/.

Bootstrap grid system have a bunch of .row placed inside a .container

Use Bootstrap's ".img-responsive class" for responsive images

boiler plate template with meta tags to start off:-

	<!DOCTYPE html>
	<html lang=”en”>
		<head>
	 		<meta charset=”utf-8”>
			<meta http-equiv=”X-UA-Compatible” content=”IE=edge”>
			<meta name=”viewport” content=”width=device-width, initial-scale=1”>
			<title></title>
			<link rel=”stylesheet” href=”css/bootstrap.css”>
		</head>

		<body>
		</body>
	</html>

Your own stylesheet should only be ordered after (and not before) the Bootstrap stylesheet because of the cascading effect so your customised stylesheet will override the default Bootstrap style whenever necessary

Breakpoints - where the page layout changes


#Intro to HTML Syntax (23 Mar 2016)

Markdown language with .md file format is supported on Github usually for README.md

Use the Mozilla Developer Network (MDN) for references on HTML

CodePen has lots of cool UI and creative coding examples


#Letter to myself as a noobie FEND (23 Mar 2016)

**Question 1 - what if you are stuck?**

Dude, its not like you are new to coding. You have created a desktop standalone app which allows the user to make a stopmotion video and email it to themselves. You have created quite a few hardware projects that incorporated some element of coding, be it a toy sound machine using motors or an interactive exhibit whose sounds and light respond to user interaction. So yeah, those articles "How to Navigate the Up and Downs of Learning to Code", "My First Month Coding: An Emotional Roller Coaster" - been there, done that. You have the technical prerequisites for this course. Moreover, if you ever get stuck in a rut, the whole World Wide Web is there to help you - Google, StackOverflow etc. You have been stuck in a rut many times and have always managed to survive somehow. So if you bomb this course, there are other reasons.

Lemme guess, if I know you well, you lack discipline and get easily distracted. You need to focus and set clear goals. You should also have fun in this course as well. Learning can be fun. For example, markdown can be fun. So here goes:

* Stay focused :triumph:
* Have fun :smiley:
* Don't give up :persevere:


**Question 2 - what are your goals?**

I want to create amazing user interfaces for applications that are a joy to use, that respond readily to every user click, scroll, touch etc, that combines interactivity with amazing design. The tool that I have been using thus far - Java/Processing, does not support user interface interactivity as much as Javascript does. Also, it is not the language of the web. The pure Java syntax is also annoyingly verbose. Also, doing layout is a purely mathematical exercise using equations for page proportions and locations  on a Cartesian plane. This is rather unnecessary and tedious unless the right tool can be used - such as CSS.

To be fair, there are also many things that Java can do that Javascript cannot - being consistent across computing platforms (rather than web platforms), many mature libraries that give Java extended capabilities, such as OpenCV and access to core native OS functionalities. But the gap is closing. Javascript is in ascendance. Look at the communities that are sprouting up - node.js, 3d.js etc. It is an exciting time to be a Javascript developer. Plus, there are now Javascript frameworks that allow you to export the app out of the browser into a native app. Isn't that amazing? Javascript now allows you to work with hardware as well - Tessel being an example. And I am a hardware guy. I want to work on IoT devices for my home or art projects. Wouldn't it be exciting if audiences could interact with your artwork across international borders?


