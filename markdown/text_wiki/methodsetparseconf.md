Set one key at a time''void **setParseConf** (string **rule name**, string **conf key**, mixed **conf value**)''Set all keys at once''void **setParseConf** (string **rule name**, array **conf key-value pairs**)''
Set the configuration for a rule parser.  For example, to tell the "include" rule what base path to use for scripts:

	:::php
	
	$wiki =& new Text_Wiki();
	$wiki->setParseConf('include', 'base', '/path/to/scripts');
	`</code>`Note:** Most rules use "render" configurations, not parse configurations.
	