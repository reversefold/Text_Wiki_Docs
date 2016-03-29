
''string **getSource** ()''

Gets the value of the ''$source'' property; i.e., the source text after all rules have been applied and matching rules have replaced source text with delimited tokens.  This is generally useful only after [parse()](MethodParse) has been called.

	:::php
	
	// [snip] create a Text_Wiki object called $wiki
	// [snip] load some source text into $text
	$wiki->parse($text);
	$source_with_delimited_tokens = $wiki->getSource();

