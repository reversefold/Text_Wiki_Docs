
`<html>``<div style="text-align: center;">``</html>`This rule is DEPRECATED.  Please use `<[code type="php"](RuleCode)>` instead.`<html>``</div>``</html>`

#   ''phpcode''''phpcode'' About This Rule Configuration Values Description

##  About This Rule
 | **Name**   | phpcode                                                                                                                                                            | 
 | --------   | -------                                                                                                                                                            | 
 | **Type**   | capturing block                                                                                                                                                    | 
 | **Syntax** | `<php>` on a line by itself at the beginning of the line, followed by the content block, followed by `</php>` on a line by itself at the beginning of the line | 

##  Configuration Values

None.

##  Description

Use this rule to mark PHP example code; the content will be colorized using highlight_string and will be surrounded with the `<?php ... ?>` tags for you.  The content will be treated as preformatted and monospaced.

For example, this markup...

	
	
	`<php>`
	    $val = "hi there!";
	    echo($val);
	`</php>`

... will result in:

`<php>`
    $val = "hi there!";
    echo($val);
`</php>`

