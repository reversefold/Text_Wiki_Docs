 About This Rule Parse Configuration Keys Render Configuration Keys Description Notes
##  About This Rule

 | **Name**          | image                                                                                                                                                                                | 
 | --------          | -----                                                                                                                                                                                | 
 | **Type**          | macro                                                                                                                                                                                | 
 | **Syntax** normal | `<nowiki>`[`</nowiki>`image ** path/to/image.ext** [**HTML attributes**] ](`</nowiki>`image ** path/to/image.ext** [**HTML attributes**] )''                                             | 
 | **Syntax** link   | `<nowiki>`[`</nowiki>`image ** path/to/image.ext** [link="**PageName**"] [**HTML attributes**] ](`</nowiki>`image ** path/to/image.ext** [link="**PageName**"] [**HTML attributes**] )'' | 

##  Parse Configuration Keys

None.

##  Render Configuration Keys

 | **Format** | **Key**      | **Type** | **Description**                                         | 
 | ---------- | -------      | -------- | ---------------                                         | 
 | ''Xhtml''  | ''base''     | string   | The base URL path to a directory of images.             | 
 | ''Xhtml''  | ''css''      | string   | The CSS class for the `<img />` tag.                      | 
 | ''Xhtml''  | ''css_link'' | string   | The CSS class for the `<a>` tag (if the image is a link). | 

##  Description

Use this macro to place an image in your output.  You may optionally link to another page in the wiki, and you may optionally indicate HTML attributes for your image, such as 'align' and 'hspace'.  There can be no spaces in the image file name, and the macro arguments must be of the form '''arg="value"'''.

You will need to configure the rule so that it knows where its images are located.  Do so with the ''[setRenderConf()](MethodSetRenderConf)'' method.

	:::php
	
	$wiki->setRenderConf('xhtml', 'image', 'base', '/images/');

For example, this markup...

	
	
	[[image photo.jpg]]
	[[image picture.jpg align="left" hspace="8"]]

... will generate this XHTML:

	
	
	`<img src="http://example.com/images/photo.jpg" />`
	`<img src="http://example.com/images/picture.jpg" align="left" hspace="8" />`

You can make the image a link to a page in the wiki by adding a ''link="..."'' argument among the HTML attributes.  This is obviously not a proper HTML attribute; the parser catches it and creates `<a href="">`...`</a>` tags for you at render-time.  If the link is to a Wiki page, the renderer get its link information from the wikilink render configuration.

	
	
	[[image photo.jpg link="HomePage"]]
	[[image picture.jpg link="http://example.com"]]

###  Notes

*  The [image](image) rule will try to guess the width and height of your image if you do not pass "width" or "height" attributes.

*  The rule allows and properly displays 'align="center"' for images; this is non-standard XHTML but a popular request for this system.
