 About This Rule Parse Configuration Keys Render Configuration Keys Description
##  About This Rule

 | **Name**   | blockquote                                                          | 
 | --------   | ----------                                                          | 
 | **Type**   | non-capturing block                                                 | 
 | **Syntax** | any line starting with one or more ''>'' signs, followed by a space | 

##  Parse Configuration Keys

None.

##  Render Configuration Keys

 | **Format** | **Key** | **Type** | **Description**                                | 
 | ---------- | ------- | -------- | ---------------                                | 
 | ''Xhtml''  | ''css'' | string   | The CSS class to use for the `<blockquote>` tag. | 

##  Description

Use this to mark block-quoted text.  Usually, the text will be indented, and line breaks should be honored.  For example...

	
	
	
	Normal text.
	
	> One level of block quoting.  The quick brown fox jumps 
	> over the lazy dog.
	> 
	> Here's another line at the same level.
	> 
	>> More indenting! Now is the time for all good men 
	>> to come to the aid of their country.
	>>> Even more indenting! Now is the time for the 
	>>> quick brown fox to come to the aid of the lazy dog.
	
	Back to normal.
	

Normal text.
One level of block quoting.  The quick brown fox jumps 
over the lazy dog.
Here's another line at the same level.
More indenting! Now is the time for all good men 
to come to the aid of their country.
Even more indenting! Now is the time for the 
quick brown fox to come to the aid of the lazy dog.
Back to normal.

