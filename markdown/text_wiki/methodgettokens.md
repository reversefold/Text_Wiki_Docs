
''string **getTokens** ([string|array **rule key names**])''

Gets the ''$tokens'' property array; i.e., the descriptions of each matching rule that has removed text from the parsed source.

By default, ''getTokens()'' returns the entire ''$tokens'' array.

If you specify a rule name as the only parameter, only those tokens for that rule will be returned.  You can also specify a sequential array of rule key names and only those tokens will be returned.

	:::php
	
	// [snip] create a Text_Wiki object called $wiki
	// [snip] load some source text into $text
	$wiki->parse($text);
	
	// get back all tokens that were matched from the source text
	$all_tokens = $wiki->getTokens();
	
	// get back only the wikilink tokens
	$wikilink_tokens = $wiki->getTokens('wikilink');
	
	// get back only the heading and toc tokens
	$heading_toc_tokens = $wiki->getTokens(array('heading', 'toc'));

