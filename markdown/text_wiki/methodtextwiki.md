
''object **Text_Wiki** (array **default rule set** default null)''

Instantiates a Text_Wiki object, optionally with a user-defined rule set.

	:::php
	
	require_once 'Text/Wiki.php';
	$wiki =& new Text_Wiki();

To re-define the default rule set, pass a sequential array of rule names as the only parameter to Text_Wiki.

	:::php
	
	// define a rule set that only looks for bold, italic, and
	// teletype inline markup
	
	$rules = array(
	    'strong',
	    'emphasis',
	    'tt'
	)
	
	$wiki =& new Text_Wiki($rules);

