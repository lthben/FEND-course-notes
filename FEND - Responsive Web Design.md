#Responsive Web Design Fundamentals

Always start off with a small viewport size first to design a  layout. Then, increase the viewport size and decide where the breakpoints are based on the content and what layouts correspond to these breakpoints.

Browser emulators across mobile and desktop devices:- [Browserstack](https://www.browserstack.com/)]

You can use Chrome's inbuilt dev tools for device emulation, e.g. on iPhone 5, Galaxy S6 etc

Can use Chrome Canary to do remote debugging on an Android device

pixel density:-
 * hardware pixels (px) vs device independent pixels (dip)
 * dip is the same as css pixels
 * pixel density ratio = px / dip

IMPORTANT! Set the viewport in CSS to set dip = css pixels:-

    <meta name="viewport" content="width=device-width,initial-scale=1.0">

set the .container class to max-width:800px instead of width:800px so that it is responsive

for making sure img do not overflow:-

	img {
		max-width:100%;
	}

for finger-touch interfaces, buttons need to be at least 48px by 48px:-

	nav a, button {
		min-width: 48px;
		min-height:48px;
	}

or

	a, button {
		padding: 1.5em;
	}

Use different stylesheets for different screen sizes:-

	<link rel="stylesheet" media="screen and (min-width:500px)" href="over500.css">

Using embedded media queries:-

	@media screen and (min-width: 500px) {
		<!--your code goes here-->
	}

Use flex-box for different grid layouts. Recapping:-

	.container {
		display:flex; /* will resize elements to fix everything into a single line */
		flex-wrap: wrap; /* gives permission to wrap to the next line if needed */
	}

Use the flex-box attribute "order" for elements to arrange the element order for different layouts. Used in layout shifter responsive design pattern. E.g.:-

	@media screen and (min-width: 700px) {
		.dark_blue { order: 4; }
		.light_blue { order: 5; }
		.green { order: 2; }
		.orange { order: 3; }
		.red {order: 1; }
	}

Responsive patterns:-
 * mostly fluid
 * column drop
 * layout shifter
 * off canvas - less important grid elements are positioned off canvas when viewport is small

example of mostly fluid + column drop:-

      .container {
        display: flex;
        flex-wrap: wrap;
      }

      .box {
        width: 100%;
      }

      @media screen and (min-width: 450px) {
        .light_blue {
          width: 50%;
        }
        .green {
          width: 50%;
        }
      }


      @media screen and (min-width: 450px) {
        .red {
          width: 33%
        }
        .orange {
          width: 67%
        }
      }


      @media screen and (min-width: 800px) {
        .container {
          width: 800px;
          margin-left: auto;
          margin-right: auto;
        }
      }

example of layout shifting design pattern:-

	@media screen and (min-width:600px) {
		.dark_blue {
			width: 25%;
			order: 1;
		}
		#container2 {
			width: 50%;
		}
		.red {
			width: 25%;
			oredr: -1;
		}
	}

example of off-canvas design pattern:-

	.nav {
	  width: 300px;
	  position: absolute;
	  /* This trasform moves the drawer off canvas. */
	  -webkit-transform: translate(-300px, 0);
	  transform: translate(-300px, 0);
	  /* Optionally, we animate the drawer. */
	  transition: transform 0.3s ease;
	}
	.nav.open {
	  -webkit-transform: translate(0, 0);
	  transform: translate(0, 0);
	}

Other advanced techniques for responsive web design:- images, typography, tables
