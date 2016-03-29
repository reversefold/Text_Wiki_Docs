Set one key at a time''void **setFormatConf** (string **format name**, string **rule name**, string **conf key**, mixed **conf value**)''Set all keys at once''void **setFormatConf** (string **format name**, string **rule name**, array **conf key-value pairs**)''
Set the configuration for a rule renderer.  For example, to tell the "Table" rule in "Xhtml" format what CSS class to use for data cells...

	:::php
	
	$wiki =& new Text_Wiki();
	$wiki->setRenderConf('Xhtml', 'Table', 'css_td', 'my_td_class');

To set all of the "Table" configuration keys for "Xhtml" at the same time...

	:::php
	
	$wiki =& new Text_Wiki();
	
	$conf = array(
	    'css_table' => 'my_table_class',
	    'css_tr' => 'my_tr_class',
	    'css_td' => 'my_td_class'
	);
	
	$wiki->setRenderConf('Xhtml', 'Table', $conf);
	`</code>`Note:** Render rule conf keys may be different from format to format.
	