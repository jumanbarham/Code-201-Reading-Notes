# The HTML <picture> 
element contains zero or more <source> elements and one <img> element to offer alternative versions of an image for different display/device scenarios.

The browser will consider each child <source> element and choose the best match among them. If no matches are found—or the browser doesn't support the <picture> element—the URL of the <img> element's src attribute is selected. The selected image is then presented in the space occupied by the <img> element.


To decide which URL to load, the user agent examines each <source>'s srcset, media, and type attributes to select a compatible image that best matches the current layout and capabilities of the display device.

The <img> element serves two purposes:

It describes the size and other attributes of the image and its presentation.
It provides a fallback in case none of the offered <source> elements are able to provide a usable image.
Common use cases for <picture>:

Art direction. Cropping or modifying images for different media conditions (for example, loading a simpler version of an image which has too many details, on smaller displays).
Offering alternative image formats, for cases where certain formats are not supported.
Note: For example, newer formats like AVIF or WEBP have many advantages, but  might not be supported by the browser. A list of supported image formats can be found in: Image file type and format guide.

Saving bandwidth and speeding page load times by loading the most appropriate image for the viewer's display.
If providing higher-density versions of an image for high-DPI (Retina) display, use srcset on the <img> element instead. This lets browsers opt for lower-density versions in data-saving modes, and you don't have to write explicit media conditions.

Content categories	Flow content, phrasing content, embedded content
Permitted content	Zero or more <source> elements, followed by one <img> element, optionally intermixed with script-supporting elements.
Tag omission	None, both the starting and ending tag are mandatory.
Permitted parents	Any element that allows embedded content.
Implicit ARIA role	No corresponding role
Permitted ARIA roles	No role permitted
DOM interface	HTMLPictureElement
Attributes
This element includes only global attributes.

Usage notes
You can use the object-position property to adjust the positioning of the image within the element's frame, and the object-fit property to control how the image is resized to fit within the frame.

Note: Use these properties on the child <img> element, not the <picture> element.

Examples
These examples demonstrate how different attributes of the <source> element change the selection of the image inside <picture>.

The media attribute
The media attribute specifies a media condition (similar to a media query) that the user agent will evaluate for each <source> element.

If the <source>'s media condition evaluates to false, the browser skips it and evaluates the next element inside <picture>.

<picture>
  <source srcset="mdn-logo-wide.png" media="(min-width: 600px)">
  <img src="mdn-logo-narrow.png" alt="MDN">
</picture>
The srcset attribute
The srcset attribute is used to offer list of possible images based on size.

It is composed of a comma-separated list of image descriptors. Each image descriptor is composed of a URL of the image, and either...

a width descriptor, followed by a w (such as 300w);
OR
a pixel density descriptor, followed by an x (such as 2x) to serve a high-res image for high-DPI screens.
<picture>
  <source srcset="logo-768.png 768w, logo-768-1.5x.png 1.5x">
  <source srcset="logo-480.png, logo-480-2x.png 2x">
  <img src="logo-320.png" alt="logo">
</picture>
The type attribute
The type attribute specifies a MIME type for the resource URL(s) in the <source> element's srcset attribute. If the user agent does not support the given type, the <source> element is skipped.

