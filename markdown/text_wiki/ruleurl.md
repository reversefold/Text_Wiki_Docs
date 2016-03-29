 About This Rule Parse Configuration Keys Render Configuration Keys Description Inline Footnote Described Image
##  About This Rule

 | **Name**               | url                                                    | 
 | --------               | ---                                                    | 
 | **Type**               | inline                                                 | 
 | **Syntax** (inline)    | `<nowiki>`http://example.com/`</nowiki>`               | 
 | **Syntax** (footnote)  | `<nowiki>`[http://example.com/]`</nowiki>`             | 
 | **Syntax** (described) | `<nowiki>`[http://example.com Example Link]`</nowiki>` | 

##  Parse Configuration Keys

None.

##  Render Configuration Keys

 | **Format** | **Key**          | **Type** | **Description**                                                                                                                                                                                             | 
 | ---------- | -------          | -------- | ---------------                                                                                                                                                                                             | 
 | ''Xhtml''  | ''target''       | string   | The HREF target for all clickable URL links; default '_blank'. *NOTE* If you are using Text_Wiki-1.2.0RC2 or earlier you will need to set this to an empty string if you do not want a new window opened. | 
 | ''Xhtml''  | ''images''       | bool     | When true (the default), URLs that point to images (.gif, .jpg,. .png) will be displayed as images instead of as links                                                                                      | 
 | ''Xhtml''  | ''img_ext''      | array    | A sequential array of filename extensions  that indicate images (defaults to 'jpg', 'jpeg', 'gif', 'png').                                                                                                  | 
 | ''Xhtml''  | ''css_inline''   | array    | The CSS class to use for inline URL `<a>` tags.                                                                                                                                                               | 
 | ''Xhtml''  | ''css_footnote'' | array    | The CSS class to use for footnoted URL `<a>` tags.                                                                                                                                                            | 
 | ''Xhtml''  | ''css_descr''    | array    | The CSS class to use for described URL `<a>` tags.                                                                                                                                                            | 
 | ''Xhtml''  | ''css_img''      | array    | The CSS class to use for `<img />` tags generated from URLs.                                                                                                                                                  | 

##  Description

The URL rule allows you to place links in the source text in three ways.

###  Inline

Normal inline (or standalone) URLs are converted in place:

	
	
	Text before http://example.com/ text after

Text before [http://example.com/](http://example.com/) text after

###  Footnote

URLs in brackets become footnote-style links, and the numbers are incremented for you.

	
	

	* This is my statement.[https://example.com/page.html]
	* This is a followup citation.[news://example.com/whatever/]


*  This is my statement.[1](https///example.com/page.html)

*  This is a followup citation.[2](news///example.com/whatever/)**Note:** If no 'css_footnote' CSS class is specified, Text_Wiki will wrap the footnote in `<sup>``</sup>` tags by default for backwards-compatibility purposes.
###  Described

URLs in brackets, with additional text inside the brackets, become described links.

	
	
	[mailto:nobody@example.com?subject=Text_Wiki My Email Address]

[My Email Address](mailto/nobody@example.com?subject=Text_Wiki)

###  Image

If your URL points to a JPG, GIF, or PNG file, the URL will be converted into an image tag.  If you use a described-link URL, the description will become the "alt" attribute of the image.

	
	
	http://example.php/image.jpg
	
	[http://example.php/image.jpg My Picture]
	`</code>``<code>`
	
	`<img src="http://example.php/image.jpg" />`
	
	`<img src="http://example.php/image.jpg" alt="My Picture" />`
	`</code>`Note:** If you want URLs that point to images to stay as inline clickable links in XHTML, set the 'images' render configuration to boolean false.
	