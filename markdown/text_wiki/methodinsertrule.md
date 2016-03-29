
''boolean **insertRule** (string **rule name** [, string **after rule name** default null])''

This method allows you to programmatically insert a new rule at the end of the rule set; or, optionally, at the beginning of the rule set, or immediately after any specified rule.

To insert a rule called "my_rule" at the end of the rule set, just pass the rule name:

	:::php
	
	$wiki =& new Text_Wiki();
	$wiki->insertRule('my_rule');

To insert the rule at the beginning of the rule set, pass an empty string as the  second parameter:

	:::php
	
	$wiki->insertRule('my_rule', '');

To insert the rule in a specific location in the rule set, specify the name of the rule **after** which the new rule should be inserted.

	:::php
	
	// Say that the current rule set is ('rule1', 'rule2', 'rule3').
	
	$after_rule = 'rule2';
	$wiki->insertRule('my_rule',$after_rule);
	
	// The rule set is now ('rule1', 'rule2', 'my_rule', 'rule3').

