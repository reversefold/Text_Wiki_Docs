Set one key at a time''void **setFormatConf** (string **format name**, string **conf key**, mixed **conf value**)''Set all keys at once''void **setFormatConf** (string **format name**, array **conf key-value pairs**)''
Set the configuration for a format renderer.  For example, to tell the "RTF" format what base font to use:

	:::php
	
	$wiki =& new Text_Wiki;
	$wiki->setFormatConf('Rtf', 'font-face', 'Arial');
	`</code>`Note:** Not all formats have configuration keys.
	