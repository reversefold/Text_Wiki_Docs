
''void **getFormatConf** (string **format name** [, string **conf key**])''

Gets the value of a configuration key for a format parser; if no key is specified, gets the entire configuration array.

	:::php
	
	$wiki =& new Text_Wiki();
	
	// get the default font face for the "RTF" format
	$dir = $wiki->getFormatConf('Rtf', 'font-face');
	
	// get all configs for the "Xhtml" format
	$conf = $wiki->getFormatConf('Xhtml');

