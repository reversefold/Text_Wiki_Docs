
First, [download and install](DownloadInstall) Text_Wiki into your [PEAR](http://pear.php.net/) library, then try the quick example below.

##  Quick Example

Here's a quick example on how to use Text_Wiki to parse wiki text and render it into XHTML:

	:::php
	
	
	// load the class file
	require_once 'Text/Wiki.php';
	
	// instantiate a Text_Wiki object with the default rule set
	$wiki =& new Text_Wiki();
	
	// when rendering XHTML, make sure wiki links point to a
	// specific base URL
	$wiki->setRenderConf('xhtml', 'wikilink', 'view_url',
	 'http://example.com/view.php?page=');
	
	// set an array of pages that exist in the wiki
	// and tell the XHTML renderer about them
	$pages = array('HomePage', 'AnotherPage', 'SomeOtherPage');
	$wiki->setRenderConf('xhtml', 'wikilink', 'pages', $pages);
	
	// load some wiki text from a file or database
	$text = "+ Header Level 1
	
	Here's a paragraph and a link to AnotherPage.
	

	* list item 1
	* list item 2
	
	Link to a NewPage like this.";
	
	// transform the wiki text into XHTML
	$xhtml = $wiki->transform($text, 'Xhtml');
	
	// display the transformed text
	echo $xhtml;
	

