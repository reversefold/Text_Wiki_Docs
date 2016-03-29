 About This Rule Parse Configuration Keys Render Configuration Keys Description Display Formatting
##  About This Rule

 | **Name**             | wikilink                                               | 
 | --------             | --------                                               | 
 | **Type**             | inline                                                 | 
 | **Syntax** normal    | `<nowiki>`AnyPageName`</nowiki>`                       | 
 | **Syntax** described | `<nowiki>`[AnyPageName displayed link text]`</nowiki>` | 

##  Parse Configuration Keys

None.

##  Render Configuration Keys

 | **Format** | **Key**             | **Type** | **Description**                                                                                             | 
 | ---------- | -------             | -------- | ---------------                                                                                             | 
 | ''Xhtml''  | ''exists_callback'' | string   | A callback bool function($page) asserting page existence                                                    | 
 | ''Xhtml''  | ''pages''           | array    | A sequential array of page names that exist in the wiki                                                     | 
 | ''Xhtml''  | ''view_url''        | string   | The base URL to view pages in the wiki                                                                      | 
 | ''Xhtml''  | ''new_url''         | string   | The base URL to create new pages in the wiki                                                                | 
 | ''Xhtml''  | ''new_text''        | string   | The text displayed after non-existent page names                                                            | 
 | ''Xhtml''  | ''new_text_pos''    | string   | Where the ''new_text'' string should be placed, either 'after' (the default) or 'before' the new page name. | 
 | ''Xhtml''  | ''css''             | string   | The CSS class for the `<a>` tag to link pages that exist.                                                     | 
 | ''Xhtml''  | ''css_new''         | string   | The CSS class for the `<a>` tag to link pages that do not exist (or the ''new_text'' link).                   | 

##  Description

As you should know by now, page names in wikis are made of WordsSmashedTogether in StudlyCapsMode.  The wikilink rule looks for WikiPages and creates links out of them.  This requires some moderate configuration to customize it for your environment.

In Text_Wiki, wiki words are allowed to have numbers in them; each digit 0-9 is treated as a lower-case character for purposes of parsing words.

The rule needs to know what pages exist in the wiki, so that when it finds a page name in the source text, it can show the proper link (either to view an existing page, or create a page that has been named but does not yet exist).  To tell Text_Wiki what wiki pages exist, use the 'exists_callback' **or** the 'pages' key in ''[setRenderConf()](MethodSetRenderConf)''.
'exists_callback' is a callback function accepting page name as parameter and returning false/true for the page's existence.
'page' is a simple array of existing pages.

	:::php
	
	// [snip] create a Text_Wiki object called $wiki
	
	// callback giving the existence of pages in the wiki
	function pageExists($page)
	{
	    if (/* finds out if the page $page exists */) {
	        return true;
	    } else {
	        return false;
	    }
	}
	
	$wiki->setRenderConf('xhtml', 'wikilink', 'exists_callback', 'pageExists');

OR

	:::php
	
	// [snip] create a Text_Wiki object called $wiki
	
	// get the list of pages in the wiki
	$pages = array(
	    'HomePage',
	    'WordsSmashedTogether',
	    'SomeOtherPages'
	);
	
	$wiki->setRenderConf('xhtml', 'wikilink', 'pages', $pages);

Now Text_Wiki needs to know where to link pages to.  There are two configuration keys for this, 'view_url' and 'new_url'.  If the parser finds a page name that exists in the 'pages' array, it will use 'view_url'; if the page is not in the 'pages' array, it will use 'new_url'.

	:::php
	
	$wiki->setRenderConf('xhtml', 'wikilink', 'view_url',
	    'http://example.php/view.php?page=%s');
	    
	$wiki->setRenderConf('xhtml', 'wikilink', 'new_url',
	    'http://example.php/new.php?page=%s');
	`</code>`Note:** Note the use of %s in the above URL strings; the %s will be replaced by the page name.  If you specify a string that does not have a %s in it, Text_Wiki will assume that the page name should go at the very end of the string.
	Finally, if the page exists, Text_Wiki will make the page name itself a link.  If the page does not exist, Text_Wiki will add some text after the page name and make that clickable instead (leading to the 'new_url').  Normally the 'new_text' is just a question mark, but you can place any literal text you like.
	`<code php>`
	
	// make the new_text a tilde
	$wiki->setRenderConf('xhtml', 'wikilink', 'new_text', '~');
	
	// make the new_text an image tag
	$wiki->setRenderConf('xhtml', 'wikilink', 'new_text',
	    `<img src="new_page.jpg" />`);

###  Display Formatting

As of Text_Wiki 0.22.0, you can choose different ways to display page links in Xhtml.  Here are some pointers:


*  If you set the ''pages'' key to false or null, Text_Wiki will assume all WikiPageNames exists; this means that Text_Wiki will always use the ''view_url'' and the ''css'' class keys when displaying links.

*  If you set ''new_text'' to blank, null, or false, Text_Wiki will use the page name itself as the ''new_url'' linked text, and use the ''css_new'' class for that link (this emulates the Wikimedia display).
