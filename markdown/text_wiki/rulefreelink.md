 About This Rule Parse Configurarion Keys Render Configuration Keys Description Display Formatting
##  About This Rule

 | **Name**             | freelink                                             |                                 
 | --------             | --------                                             |                                 
 | **Type**             | inline                                               |                                 
 | **Syntax** normal    | `<nowiki>`((Non-Standard Wiki Page Name))`</nowiki>` |                                 
 | **Syntax** described | `<nowiki>`((Non-Standard Wiki Page Name              | displayed link text))`</nowiki>` | 

##  Parse Configurarion Keys

None.

##  Render Configuration Keys

 | **Format** | **Key**          | **Type** | **Description**                                                                                             | 
 | ---------- | -------          | -------- | ---------------                                                                                             | 
 | ''xhtml''  | ''pages''        | array    | A sequential array of page names that exist in the wiki                                                     | 
 | ''xhtml''  | ''view_url''     | string   | The base URL to view pages in the wiki                                                                      | 
 | ''xhtml''  | ''new_url''      | string   | The base URL to create new pages in the wiki                                                                | 
 | ''xhtml''  | ''new_text''     | string   | The text displayed after non-existent page names                                                            | 
 | ''Xhtml''  | ''new_text_pos'' | string   | Where the ''new_text'' string should be placed, either 'after' (the default) or 'before' the new page name. | 
 | ''Xhtml''  | ''css''          | string   | The CSS class for the `<a>` tag to link pages that exist.                                                     | 
 | ''Xhtml''  | ''css_new''      | string   | The CSS class for the `<a>` tag to link pages that do not exist (or the ''new_text'' link).                   | 

##  Description

As you should know by now, page names in wikis are usually indicated by WordsSmashedTogether in StudlyCapsMode.  However, some people want to use arbitrary strings of text as page names; these are called "free links" (as opposed to "wiki links").

Free links work the same way as wiki links: you type them in (surrounded by double-parentheses) and if the page exists, Text_Wiki links to it; if not, Text_Wiki shows a clickable link to create the free-linked page.  The freelink rule looks requires some moderate configuration to customize it for your environment, just like the [wikilink](RuleWikilink) rule.

The rule needs to know what pages exist in the wiki, so that when it finds a page name in the source text, it can show the proper link (either to view an existing page, or create a page that has been named but does not yet exist).  To tell Text_Wiki what wiki pages exist, use the 'pages' key in ''setRenderConf()''.  Here is an example for the XHTML format.

	:::php
	
	// [snip] create a Text_Wiki object called $wiki
	
	// create list of free-link page names in the wiki ...
	$pages = array(
	    'Free linked page',
	    'some special name',
	    'Other page'
	);
	
	// ... and tell Text_Wiki about them,
	$wiki->setRenderConf('xhtml', 'freelink', 'pages', $pages);
	`</code>`Note:** You can mix wikilink page names in with the freelink page names if you like; the freelink rule will ignore the wikilink page names.
	Now Text_Wiki needs to know where to link pages to.  There are two configuration keys for this, 'view_url' and 'new_url'.  If the rule finds a page name that exists in the 'pages' array, it will use 'view_url'; if the page is not in the 'pages' array, it will use 'new_url'.
	`<code php>`
	
	$wiki->setRenderConf(
	    'xhtml',
	    'freelink',
	    'view_url',
	    'http://example.php/view.php?page=%s'
	);
	
	$wiki->setRuleConf(
	    'xhtml',
	    'freelink',
	    'new_url',
	    'http://example.php/new.php?page=%s'
	);
	`</code>`Note:** Pay attention to the use of %s in the above URL strings; the %s will be replaced by the page name.  If you specify a string that does not have a %s in it, Text_Wiki will assume that the page name should go at the very end of the string.
	Finally, if the page exists, Text_Wiki will make the page name itself a link.  If the page does not exist, Text_Wiki will add some text after the page name and make that clickable instead (leading to the 'new_url').  Normally the 'new_text' is just a question mark, but you can place any literal text you like.
	`<code php>`
	
	// make the new_text displayed link text a tilde
	$wiki->setRenderConf('xhtml', 'freelink', 'new_text', '~');
	
	// make the new_text an image tag
	$wiki->setRenderConf('xhtml', 'freelink', 'new_text',
	    `<img src="new_page.jpg" />`);

###  Display Formatting

As of Text_Wiki 0.22.0, you can choose different ways to display page links in Xhtml.  Here are some pointers:


*  If you set the ''pages'' key to false or null, Text_Wiki will assume all WikiPageNames exists; this means that Text_Wiki will always use the ''view_url'' and the ''css'' class keys when displaying links.

*  If you set ''new_text'' to blank, null, or false, Text_Wiki will use the page name itself as the ''new_url'' linked text, and use the ''css_new'' class for that link (this emulates the Wikimedia display).
