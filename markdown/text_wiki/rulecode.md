 About This Rule Parse Configuration Keys Render Configuration Keys Description
##  About This Rule

 | **Name**             | code                                                                                                                                                  | 
 | --------             | ----                                                                                                                                                  | 
 | **Type**             | capturing block                                                                                                                                       | 
 | **Syntax** plain     | ''`'' on a line by itself at the beginning of the line, followed by content block, followed by ''`'' on a line by itself at the beginning of the line | 
 | **Syntax** with type | ''`...`{type="**type**"}'' to indicate the type of code; e.g., ''type="PHP"'' or ''type="HTML"''                                                      | 

##  Parse Configuration Keys

None.

##  Render Configuration Keys

 | **Format** | **Key**      | **Type** | **Description**                                                           | 
 | ---------- | -------      | -------- | ---------------                                                           | 
 | ''Xhtml''  | ''css''      | string   | The CSS class to use for the `<pre>` tag that wraps around the `<code>` tags. | 
 | ''Xhtml''  | ''css_code'' | string   | The CSS class to use for the `<code>` tag when no code type is specified.   | 
 | ''Xhtml''  | ''css_php''  | string   | The CSS class to use for the `<code>` tag when type="php".                  | 
 | ''Xhtml''  | ''css_html'' | string   | The CSS class to use for the `<code>` tag when type="html".                 | 

##  Description

Use this rule to mark a generic code example.  Text inside the code block will be treated as preformatted and monospaced. This markup:

	
	
	 `<code>`
	 line 1
	 line 2

`</code>`
... will generate this output:

	
	
	line 1
	line 2

If you specify a type of PHP, Text_Wiki will colorize the code for you and print `<?php ... ?>` tags around it.  For example, this markup ...

	
	
	 `<code type="php">`
	 // comment
	 $variable = 'Hello world!';
	 echo($variable);

`</code>`
... generates this output:

	:::php
	
	// comment
	$variable = 'Hello world!';
	echo($variable);

Similarly, this specifying HTML code like this...

	
	
	 `<code type="html">`
	 `<!-- comment -->`
	 `<p>`A paragraph `<br />` and line break.`</p>`

`</code>`
Generates this output (note the `<html>` tags):

	:::html
	
	`<!-- comment -->`
	`<p>`A paragraph `<br />` and line break.`</p>`

You can specify any code type you like, e.g. "shell", but tags are added only to PHP and HTML code, and colorization only occurs for PHP code.  Others may be added later.

