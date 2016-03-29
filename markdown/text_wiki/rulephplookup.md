 About This Rule Parse Configuration Keys Render Configuration Keys Description
##  About This Rule

 | **Name**   | phplookup                                                                    | 
 | --------   | ---------                                                                    | 
 | **Type**   | macro                                                                        | 
 | **Syntax** | `<nowiki>`[`</nowiki>`php **function-name**](`</nowiki>`php **function-name**)'' | 

##  Parse Configuration Keys

None.

##  Render Configuration Keys

 | **Format** | **Key** | **Type** | **Description**                | 
 | ---------- | ------- | -------- | ---------------                | 
 | ''Xhtml''  | ''css'' | string   | The CSS class for the `<a>` tag. | 

##  Description

Creates a lookup-link to the PHP manual for the given function name; it automatically ignores () at the end of a the function name.  For example, this markup...

	
	
	[[php function_exists()]]

... creates this XHTML:

	
	
	`<a href="http://php.net/function_exists">`function_exists()`</a>`

Like so:  function_exists()

