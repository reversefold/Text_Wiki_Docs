
''string **transform** (string **source text** [, string **render type** default 'Xhtml')''

This method will parse, render, and return the output for wiki source text according to the defined rule set.  It will load the parse, format, and render class objects as it goes.

The ''transform()'' method actually calls ''[parse()](MethodParse)'' and ''[render()](MethodRender)'' for you, accomplishing both steps with only one call.

	:::php
	
	// [snip] create a Text_Wiki object called $wiki
	// [snip] load some wiki text into a variable called $text
	
	// parse and render the text
	$xhtml = $wiki->transform($text, 'xhtml');
	
	// output the results
	echo $xhtml;

