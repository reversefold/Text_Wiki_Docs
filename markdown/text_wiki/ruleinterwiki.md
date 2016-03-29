 About This Rule Parse Configuration Keys Render Configuration Keys Description
##  About This Rule

 | **Name**             | interwiki                                                       | 
 | --------             | ---------                                                       | 
 | **Type**             | inline                                                          | 
 | **Syntax** normal    | `<nowiki>`SiteName:PageName`</nowiki>`                          | 
 | **Syntax** described | ''[`<nowiki>`SiteName:PageName`</nowiki>` Show this text instead]'' | 

##  Parse Configuration Keys

None.

##  Render Configuration Keys

 | **Format** | **Key**    | **Type** | **Description**                                                                                                         | 
 | ---------- | -------    | -------- | ---------------                                                                                                         | 
 | ''Xhtml''  | ''sites''  | array    | An array of key-value pairs where the key is the text of the interwiki site name and the value is the URL for that site | 
 | ''Xhtml''  | ''target'' | string   | The target for interwiki links; e.g., '_blank'                                                                          | 
 | ''Xhtml''  | ''css''    | string   | The CSS class to use for the `<a>` tag.                                                                                   | 

##  Description

Interwiki is a way of representing wiki pages on other wikis.  To mark an interwiki link, type the name of the site, a colon, then the name of the page on the interwiki site.

Text_Wiki needs to know the URL for the various interwiki sites so it make clickable links; to tell Text_Wiki the site names and urls, use the ''[setRenderConf()](MethodSetRenderConf)'' method.  The array key should be the name of the site, and the array value should be the URL part leading up to the page-value.

	:::php
	
	// [snip] create a Text_Wiki object called $wiki
	
	// set up an array of interwiki site names and urls
	$sites = array(
	    'MeatBall'    => 'http://www.usemod.com/cgi-bin/mb.pl?%s',
	    'Advogato'    => 'http://advogato.org/%s',
	    'Wiki'        => 'http://c2.com/cgi/wiki?%s'
	);
	
	// configure the interwiki rule
	$wiki->setRenderConf('xhtml', 'interwiki', 'sites', $sites);
	`</code>`Note:** Pay attention to the use of %s in the above URL strings; the %s will be replaced by the page name.  If you specify a string that does not have a %s in it, Text_Wiki will assume that the page name should go at the very end of the string.
	