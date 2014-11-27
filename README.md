email
=====

Email Development

# Cross browser/email client background images. 

With the use of VML & CSS we are able to achieve background image support in the majority of mobile, web and desktop email clients. This technique provides a full background image applied to any table cell or div.

_Extended research and development inspired by the bullet-proof background tool developed by Stig over at Campaign Monitor http://backgrounds.cm/_

**Benefits**
* Better responsive design
* System text incorporated within the design
* Lower filesize for animated content (JPEG background with GIF overlay)
* Can be used as patterned background or as fixed/single image background.

**Support**
* Outlook 2007/10/13 
* Outlook 03/Express/Mail
* iPhone iOS 7/iPad	
* Outlook.com	
* Apple Mail 6.5
* Yahoo! Mail	
* Google Gmail	
* Android 4 (Gmail) +

## What is VML  
- http://en.wikipedia.org/wiki/Vector_Markup_Language

Vector Markup Language (VML) is an XML-based file format for two-dimensional vector graphics.

Basically VML is used by Microsoft Office software, in our case Outlook. We use this language in order to render background image in Outlook.

## How To ##

In this example you'll see a JPEG background image with a GIF overlay. Historically the only way to achieve this would be to either make the whole image an animated GIF (which would be very heavy in filesize) or to slice the image into multiple slices.

[Example](http://www.nik.net.au/nap/email/thanksgiving/example.html)

[Send yourself a test](https://www.putsmail.com/tests/0f7ab73c-9ab1-4913-b7b2-7849b48aa9ea)

`<table width="600" align="center" border="0" cellspacing="0" cellpadding="0">`  
`<tr>`  
`<td width="600" height="469" background="http://www.nik.net.au/nap/email/thanksgiving/img-desktop_final_V2.jpg"  bgcolor="#FFFFFF" valign="top">`   
`<!--[if gte mso 9]><v:rect xmlns:v="urn:schemas-microsoft-com:vml" href="http://www.nik.net.au" fill="true" stroke="false" style="width:600px;height:469px;"><v:fill type="tile" src="http://www.nik.net.au/nap/email/thanksgiving/img-desktop_final_V2.jpg" color="#FFFFFF" /><v:textbox inset="0,0,0,0"><![endif]-->`  
`<a href="http://www.nik.net.au.com">`  
`<img src="http://www.nik.net.au/nap/email/thanksgiving/text-desktop_final_V2.gif" border="0" style="display:block" />`   
`</a>`  
`<!--[if gte mso 9]></v:textbox></v:rect><![endif]-->`  
`</td>`  
`</tr>`  
`</table>`

### Closer look at the code.

`<table width="600" align="center" border="0" cellspacing="0" cellpadding="0">`  
`<tr>`  
**Here i've set the background image to the table cell, also set the height and width to be the same as the background image.**   
`<td width="600" height="469" background="http://www.nik.net.au/nap/email/thanksgiving/img-desktop_final_V2.jpg"  bgcolor="#FFFFFF" valign="top">`   
**This is the clever code that outlook reads to render the background image.
Here we are creating a VML rectangle element (v:rect) and using VML fill element to give that rectangle a background.**   
`<!--[if gte mso 9]><v:rect xmlns:v="urn:schemas-microsoft-com:vml" href="http://www.nik.net.au" fill="true" stroke="false" style="width:600px;height:469px;">`
** Using inline CSS we can set the width and height of the v:rect, this should be the width and height of your backghround image.**     
`<v:fill type="tile" src="http://www.nik.net.au/nap/email/thanksgiving/img-desktop_final_V2.jpg" color="#FFFFFF" />`   
**VML textbox element holds any content that is overlaying the background (inside of the v:rect). By setting the inset values to 0,0,0,0 it ensures there is no padding or margins for the background image.**   
`<v:textbox inset="0,0,0,0">`     
`<![endif]-->`   
** Content can go in here, this includes system text, additional images etc **  
`<a href="http://www.nik.net.au">`  
`<img src="http://www.nik.net.au/nap/email/thanksgiving/text-desktop_final_V2.gif" border="0" style="display:block" />`   
`</a>`   
** Closing off the VML markup. **  
`<!--[if gte mso 9]></v:textbox></v:rect><![endif]-->`  
`</td>`  
`</tr>`  
`</table>`
