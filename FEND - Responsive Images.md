#Responsive Images

Images take up 60% of bandwidth during downloads!

Setting up mobile dev environment with Chrome Canary on PC and Chrome Beta on mobile

Image size = number of pixels x bits per pixel -> have as low resolution as poss and as high compression as poss

calc()

design for both landscape and portrait viewport orientations, e.g. using viewport width or height attributes as references:-

	height: 50vh;
	width: 25vw;

	width: 100vmax;
	height: 100vmax

Be aware of the diff between raster and vector images. Use vector whenever it has to be scaled.

Be aware of large images loading on slow internet connectivity. Test the download times using the Network tool in the Chrome Dev Tools.

[ImageMagick](www.imagemagick.org) - free open source tool for batch processing images, e.g. converting from jpeg to webp

Compress high resolution jpeg images with `quality: 20` to reduce file size using lossy compression

There is also GraphicsMagick, ImageOptim

[PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/?url=simpl.info%2Fcssfilters) - dev tool to check for optimised images, has various forms such as a grunt package [grunt-responsive-images](https://addyosmani.com/blog/generate-multi-resolution-images-for-srcset-with-grunt/)

Use [Grunt](https://24ways.org/2013/grunt-is-not-weird-and-hard/) to help automate build processes

	* create a package.json and Gruntfile.js
	* install npm and the grunt CLI
		npm install
		npm install -g grunt-cli

Use the <figure> caption like this:-
	<figure>
		<img .....>
		<figcaption>mycaption</figcaption>
	</figure>

Instead of downloading multiple images and incurring multiple server requests, use a single sprite sheet containing all images as the background and select the image by setting the background-position for that particular element like [this](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Images/Implementing_image_sprites_in_CSS_)

Avoid images wherever possible. CSS can be used to create some image types such as gradients or textures, and do tricks like simple animation, transitions or filters, but use sparingly. Nice typography design can be used in place of images.

`background-image: cover;` vs `background-image: contain;` -> two ways of sizing a background image

Set up a simple HTTP server by:- `python -m SimpleHTTPServer` and access it at http://127.0.0.1:8000

Some symbols and icons can be used as part of text fonts rather than images. [Unicode](http://unicode-table.com/en/sets/) has hundreds of thousands of characters. The unicode for characters can be pasted directly into your html like text.

There are also icon fonts like [Zocial](http://zocial.smcllns.com/) and [Font Awesome](http://fortawesome.github.io/Font-Awesome/) that can be used in place of images

Inline images with SVG and Data URIs with code rather than incurring a http request

If the same image is to be reloaded multiple times for different pages for a website, it is better to load it as an external source file so that the browser can cache it, rather than inlining it, which means the browser will have to keep reloading the same image over and over again.

`srcset` and `sizes` attributes:- e.g. `<img src="small.jpg" srcset="small.jpg 500w 1x, small-HD.jpg 500w 2x, medium.jpg 1000w 1x" sizes="(max-width: 250px) 100vw, 50vw" alt="image_name"` -> the CSS needs to match in order to do the actual resizing

An [article](http://www.html5rocks.com/en/mobile/high-dpi/) on a comprehensive strategy list for high dpi images

Can consider using the WebP image format. E.g.:-

	<picture>
		<source srcset="kittens.webp" type="image/webp">
		<img src="kittens.jpg" alt="Two kittens"> <!--will fall back to jpg if webP is not supported-->
	</picture>

Art Direction (which image to select based on viewport size) can be done using the <picture> tag with media queries:-

	<picture>
		<source media="min-width: 1000px" srcset="bird_whole_1x.jpg 1x, bird_whole_2x.jpg 2x"
		<source media="min-width: 500px" srcset="bird_cropped_1x.jpg 1x, bird_cropped_2x.jpg 2x" <!--using a cropped version for smaller viewports -->
		<img src="bird_small.jpg" alt="some bird">
	</picture>

Install Chrome extensions Lynx or ChromeVox to test your website's experience for visually impaired users. The <img alt> attribute is important for describing your images