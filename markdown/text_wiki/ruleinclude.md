 About This Rule Parse Configuration Keys Render Configuration Keys Description
##  About This Rule

`<html>``<span style="color: red;">``</html>`Warning:`<html>``</span>``</html>` This dangerous and powerful markup rule is **disabled by default**.  If you enable it, careless use can compromise the security of your system.

 | **Name**   | include                                                                                        | 
 | --------   | -------                                                                                        | 
 | **Type**   | macro                                                                                          | 
 | **Syntax** | `<nowiki>`[`</nowiki>`include** path/to/script.php**](`</nowiki>`include** path/to/script.php**)'' | 

##  Parse Configuration Keys

 | **Key**  | **Type** | **Description**                         | 
 | -------  | -------- | ---------------                         | 
 | ''base'' | string   | The base path to your scripts directory | 

##  Render Configuration Keys

None.

##  Description

This rule will run a PHP script of your choosing, capture the output of that script, and place it in the source text.  That output will then be subject to parsing by the remaining Text_Wiki rules and rendered appropriately.

All your ''include''-able scripts need to be in the same base directory path (although you can further organize that directory into subdirectories).  You can set that base path with the ''[setParseConf()](MethodSetParseConf)'' method:

	:::php
	
	// [snip] create a Text_Wiki object ($wiki)
	$wiki->setParseConf('include', 'base', '/path/to/scripts/');

