
''string **render** ([string **output format** default 'Xhtml')''

This method will look at the current values of ''$source'' and ''$tokens'', render token elements back into the source in the specified output format, and return the results.

	:::php
	
	// [snip] create a Text_Wiki object called $wiki
	// [snip] load source text into $text
	
	// parse the source text
	$wiki->parse($text);
	
	// render the parsed text into XHTML
	$output = $wiki->render();
	
	// display the rendered output
	echo $output;

