This polyfill adds a "min-width" attribute to the viewport meta tag. This is useful
if a page is responsive, but still has a minimum width. For example, if you have a
page which scales down to 500px, mobile browsers will render it at 1024px unless you
set a viewport. The problem is that if you set
`<meta name="viewport" content="width=500"/>`, the width will be fixed at 500px, and
won't properly use extra space on tablets. If you set
`<meta name="viewport" content="width=device-width"/>`, it will be rendered at the
correct size for all devices, but will start out zoomed in on devices smaller than
500px.

## Usage

Add a meta tag containing the standard content, plus your `min-width` (in this
example it's 500px). **After** that, include this JavaScript file. The JS has to be
loaded after, because it needs the meta tag to be in the DOM already. We could wait
for a load event, but that would cause page flickering.

    <meta name="viewport" content="width=device-width, initial-scale=1.0, min-width=500"/>
    <script type="text/javascript" src="viewport-min-width.js"/>

