
''void **getRenderConf** (string **format name**, string **rule name** [, string **conf key**])''

Gets the value of a configuration key for a rule rendered in a specific format; if no key is specified, gets the entire configuration array.

	:::php
	
	$wiki =& new Text_Wiki();
	
	// get the list of pages that the wikilink rule knows about
	$dir = $wiki->getRenderConf('Xhtml', 'Wikilink', 'pages');
	
	// get all configs for the "Xhtml" format "wikilink" rule
	$conf = $wiki->getRenderConf('Xhtml', 'Wikilink');

