# image 
The image should be dark, and not have a lot of contrast-y edges.

Picking an image is up to you, but let’s say it isn’t particularly dark. You could darken it in an image editing program, or, with CSS, overlay a transparent color. Probably the cleanest way to do that is to use multiple backgrounds, but that isn’t super obvious how to do. The trick is using a gradient that doesn’t gradient-ize (doesn’t fade from color to color, is just solid).

.darken {
  background-image: 
    linear-gradient(
      rgba(0, 0, 0, 0.5),
      rgba(0, 0, 0, 0.5)
    ),
    url(shoes.jpg);
}

And while a black overlay is simplest and most versatile, you can certainly find colored overlays as well.

Indeed with this method you can color however you want from the comfort of CSS:


White Text
The text has to be white — I dare you to find a counter-example that’s clean and simple. Seriously. Just one.

I find this to be true as well, at least when trying to be classy whatsoever. Garbage magazines tend to go with yellow.


Full Page Images
One way in which it’s rather unavoidable to set text on an image is when you make the entire screen fill with a background image. We’ve covered how to do that before, you’re best bet is:

body {
  background: /* do whatever tinting and stuff here */;

  /* This will ensure everywhere is covered */
  background-size: cover;
}

And by the way, if you wanted to cover the entire screen like this, but then be able to scroll down for more, you could set the top area as having a height of 100vh units.


Browser support varies a bit there. You might wanna have a fixed height fallback and/or do it with JavaScript.

Text-in-a-box
This is dead simple and very reliable. Whip up a mildly-transparent black rectangle and lather on some white text. If the overlay is opaque enough, you can have just about any image underneath and the text will still be totally legible.

Works with any contrast-y color combination.


With a single line of text, this is easy. But if there is any chance of the text breaking, it’s harder. You could leave the title as display: block; but it’s not as elegant perhaps as inline. But with inline, you need to take care that the spacing around the line breaks isn’t awkward.

We’ve covered this before. I think it’s coming down to box-decoration-break as being the way forward:

.title { 
  background-color: black;
  color: #fff; 
  display: inline;
  padding: 0.5rem;
  
  -webkit-box-decoration-break: clone;
  box-decoration-break: clone;
}

Blurring
A surprisingly good way for making overlaid text legible is to blur part of the underlying image.

One way to do that is to to have a section of the area inherit the same background, position it the same (fixed attachment is one way), then blur it.

.module {
  background: url(http://s3-us-west-2.amazonaws.com/s.cdpn.io/3/skyscrapers.jpg);
  background-attachment: fixed;
  overflow: hidden;
}
.module > header {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  padding: 20px 10px;
  background: inherit;
  background-attachment: fixed;
}
.module > header::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: inherit;
  background-attachment: fixed;
  -webkit-filter: blur(12px);
  filter: blur(12px);
}

That’s using a color bar in addition to the blur, but you don’t necessarily have to. You could blur it enough it works OK:


Softening just part of the image like this Erik is calling a scrim.

A scrim is a piece of photography equipment that makes light softer. Now it’s also a visual design technique for softening an image so overlaid text is more legible.

Floor Fade
The floor fade is when you have an image that subtly fades towards black at the bottom, and then there’s white text written over it.

This is perhaps fairly obvious since we’ve been using gradients to tint, but…

.module {
  background: 
    linear-gradient(
      to bottom,
      rgba(0, 0, 0, 0),
      rgba(0, 0, 0, 0.6)
    ),
    url(skyscrapers.jpg);
}

You can possibly get away with less image darkness if you combo it with a little text shadow:

.title {
 text-shadow: 0 1px 0 black;
}
In closing…

It’s pretty fun to find other ways and play with combining these techniques
I’m sure you’ll find browsers in which these demos fail. Maybe we can use the comment thread to discuss fallback possibilities.
Ad for mailchimp
SPONSORED
Create an effective campaign & grow sales using insights on what people are more likely to buy next.

Ad for Algolia
SPONSORED
6 open source UI libraries. 11 API clients. 1 hour to build. Take the pain out of building and maintaining site search with our hosted API.
Ad for hotjar
SPONSORED
Understand how users are really experiencing your site without drowning in numbers. Sign up for a 15-day business trial!
Ad for DataStax
SPONSORED
Deliver applications faster with REST, GraphQL, CQL, and JSON/Document APIs. Try Astra DBaaS with 5 GB free.
Ad for Contentful
SPONSORED
Don't' let your CMS dictate your tech. Meet Contentful, the API-first content platform for your preferred tech stack.
OUR LEARNING PARTNER
Frontend Masters logo
Frontend Masters
Need front-end development training?
Frontend Masters is the best place to get it. They have courses on all the most important front-end technologies, from React to CSS, from Vue to D3, and beyond with Node.js and Full Stack.

ads via Carbon
Limited time offer: Get 10 free Adobe Stock images.
ads via Carbon
Instant GraphQL Backend
Instant GraphQL Backend
Add state to your Javascript apps with Fauna. Generous free tier. Try now!
The Divi Theme
The Divi Theme
Download the Ultimate WordPress Theme including our advanced Drag & Drop builder
Frontend Masters logo
Need front-end development training?
Frontend Masters is the best place to get it. They have courses on all the most important front-end technologies, from React to CSS, from Vue to D3, and beyond with Node.js and Full Stack.

Comments
Martijn
Permalink to comment# December 12, 2014
I like the blurring option. Being something of a photography hobbyist, the blur suggests depth of field (even though blur != out of focus), which is very appealing to me. However, I feel the blurring should be “gradientized” for a smooth transition from image to blurred part.

Mihkel Eidast
Permalink to comment# December 12, 2014
Cool post. Many designers get this stuff wrong.

I didn’t know about box-decoration-break before, but I’m thrilled to know it exists.

You use a simple background-image in this post, but I don’t think it’s very mobile-friendly (especially if you have a fullscreen background-image). Maybe you could do a post about how to do responsive background-images. I have been doing them with an absolutely positioned background container and picture.

Thanks for sharing these cool tips!

Justin Avery
Permalink to comment# December 16, 2014
Hey Mihkel,

The responsive background-image technique you have mentioned sounds interesting, could you post a codepen example?

Is there any reason why you wouldn’t just declare different media queries in the CSS to define different background-image requirements?

Mihkel Eidast
Permalink to comment# December 16, 2014
I’ll make a CodePen later today and reply it here.

Using CSS media queries is definitely an option. But in my case, the images are coming from WordPress usually, which means that I would have to PHP that CSS inline. (And I hate inline CSS.)

Timothy Long
Permalink to comment# December 12, 2014
On the blurring technique, going to 150% width/height on “.module > header::before” helps spread the blur more evenly across the header.

Chris Coyier
Permalink to comment# December 12, 2014
Yeah! Good idea. On the example that doesn’t have the black bar, I ended up using some scale() action to do that same kinda thing.

Jozsef
Permalink to comment# December 12, 2014
Interesting article. I always wondered how to get rid of the vertical space of inline elements when they have a background. I usually used line-height on the block parent element to lower the vertical space between lines. But if the design amended bigger space between lines, then I got into trouble. So thanks for pointing out this feature(box-decoration-break). Also the color tintig of the images are original. I have one of my methods also ( http://thecsscoder.com/blog/css/color-splash/ ) . The blur + scew effect was genius.

Jacob Burden
Permalink to comment# December 12, 2014
I’m so glad you made this post. Text on images is something I’ve been experimenting with recently and these example look way easier to implement.

The way I went about it seems crufty now, but it was more like this:

.splash {
  position: relative;
  background-position: top center;
  background-repeat: no-repeat;
  background-size: cover;
  background-image: url();
}
.splash:before {
  content: "";
  display: block;
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  pointer-events: none;
  background: rgba(0,0,0,0.25);
}
Here’s some examples using that method —



Luke
Permalink to comment# December 22, 2014
I use a similar approach on sites for clients that have visitors that still use those old dusty browsers.

I use a nested block element as the background instead of using the :before or :after selectors. I like this method because it works well across browsers and it isn’t too much extra work. It also gives you the ability to animate the background element as well.

Brad S
Permalink to comment# December 12, 2014
I’d really like to see some examples where the image isn’t a background in CSS but a regular IMG as part of the content with the overlay then applied.

Dalton
Permalink to comment# December 12, 2014
I usually do this with an absolutely positioned headline inside a relatively positioned parent container, like so:



Remy Sheppard
Permalink to comment# December 12, 2014
I’m putting together a video background for a business site, and I had to use white text (just looks the best), but the video is bright colors. I went through a couple of different things before deciding that a slight text-shadow, at like 80px diffused it enough that the shadow wasn’t obvious, but made the words pop.

Great post!

Amelia BR
Permalink to comment# December 12, 2014
A couple other tricks to add to the toolchest:

Courtesy of Codepen user Kseso:

If you want to force line breaks between words in your overlay text, without having extra elements (or the scripts to create them), you can use the word-spacing property to force the text to wrap. You just add a full window’s worth of space after every word with word-spacing: 100vw.

Courtesy of me playing around with Kseso’s pen and the examples from this post:

If you have inline blocks of text with a background, and you want line spacing other than the standard 1.4em, the background overlaps in ugly ways. However, you can use the single-color gradient technique to create a background image of just the right size.



Regarding Chris’s question on compatibility:

This is a tricky issue whenever you’re using graphical effects to ensure basic legibility; if the effects don’t work, you might end up with unreadable white text on a light-colored image.

My inline color-block example (above) ensures basic legibility by setting a fallback solid background color on the span before over-riding it with the transparent background gradient. The result on the IE9 emulator isn’t as pretty, but it is legible and has the same overall design. (IE8 falls apart on other aspects of the design, but again is still legible.)

However, if you’re applying the tinted overlay using layered background images, it’s more difficult to fix with ordinary CSS fallback rules. You would need to either have a separate image file fallback (e.g., a server-generated tinted image, lots of extra work) or you would have to replace the entire hero image with solid color.

The other option is to use an @supports rule to test for gradient support (or filters, text-shadows, or whatever else you’re using to create contrast) and otherwise use completely different font color and background settings. The problem with that, of course, is that IE and Safari don’t support @supports, so they would get your legacy-browser fallback effect even though they do support gradients and text-shadows.

dr. Rosita
Permalink to comment# December 15, 2014
I think just build every image in photoshop like what we wanted then hang on our website..

Teelah
Permalink to comment# December 15, 2014
This is an awesome read. Great for SEO, and this was is best practices. This is becoming a very popular technique.

Sahil Gupta
Permalink to comment# December 15, 2014
thanks for the post. I was currently working on a project in which i was using the same. You really save lot of time which i will need to invest in experimenting with it.

Jeffrey Sweeney
Permalink to comment# December 15, 2014
Awesome tips (particularly like the image blur one!)

Another trick I’ve used is to give text a very subtle shadow.
It’s unnoticeable unless you’re really looking for it, but it can make the text slightly more legible.

Michiel Bijl
Permalink to comment# December 16, 2014
You can—of course—also combine these techniques. The pen uses a combination of a dark background gradient and white text with a shadow, emphasised on hover/focus:

See the Pen Responsive Conference List by Michiel Bijl (@Michiel) on CodePen.

Sara Soueidan
Permalink to comment# December 16, 2014
I love this post! :)

Worth adding that tinting images becomes less “hacky” once CSS blend modes have better browser support.

Lea Verou posted a snippet a while ago that tints an image using just a couple of lines of CSS. Dudley Storey elaborated in his article with further examples and links to many resources that are also worth checking out.

—S

Ed Henderson
Permalink to comment# December 16, 2014
This article arrived at the exact time I was looking for it. Thank you Sir.

userAlexander
Permalink to comment# December 17, 2014
Not work in Safari and IE9-

Ryan
Permalink to comment# December 17, 2014
I quite like the examples with a splash of semi-transparent color behind them, or a faint gradient.

I’ve always found that blurring parts of an image for foreground content feels like there’s an optical illusion from something covering up the lens in the photo (like a finger over the edge by accident, or something stuck on the lens) :)

Gabriel
Permalink to comment# December 19, 2014
For the 100vh, I usually specify padding as well just in case either a browser doesn’t support vh, or more often, the content is too big for the viewport. And of course instead of height, I use min-height.

Matt Kreiling
Permalink to comment# December 21, 2014
As far as applying background color to a block of text, I recently came across this method, using box-shadow.

box-shadow: -15px 0 0 0px white, 15px 0 0 0px white;

-via Sophie Shepard

Seems like if might have more support than box-decoration-break: clone

Chris
Permalink to comment# December 25, 2014
There are some gaps of information in your blurring demonstration:

1.In order to get that clean, crisp border along the blurred section you need to position the generated content twenty pixels or so down from the top of your header element
2.The header element needs to be given an overflow value of hidden.
3. And the h1 element needs to be higher on the z-index (as written, my text kept getting blurred out)

the actual page markup reveals all this.
hope this helps somebody out!

Chris
Permalink to comment# December 25, 2014
oops, i meant up, not down.
ie, top: -20px

Orangestar
Permalink to comment# January 4, 2015
Oh hey cool comments are still open here.

I did a black-on-white overlay with my current site design. The design’s not the best but I like how it looks. I got inspired to do it watching The Weather Channel.

A method other than using 100vh that’s more browser-compatible is to set html, body, and your container to 100% in height. Here’s a codepen.



