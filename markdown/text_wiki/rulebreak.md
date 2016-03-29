 About This Rule Parse Configuration Keys Render Configuration Keys Description
##  About This Rule

 | **Name**   | break                                          | 
 | --------   | -----                                          | 
 | **Type**   | inline                                         | 
 | **Syntax** | any line ending with a space and an underscore | 

##  Parse Configuration Keys

None.

##  Render Configuration Keys

 | **Format** | **Key** | **Type** | **Description**                          | 
 | ---------- | ------- | -------- | ---------------                          | 
 | ''Xhtml''  | ''css'' | string   | The CSS class to use for the `<br />` tag. | 

##  Description

Use this to explicitly mark a line break.  Use in lists, tables, etc. to break lines without breaking the element.

	
	
	

	* The quick brown fox jumps over the lazy dog.
	* The quick brown _
	fox jumps over _
	the lazy dog.

	* The quick brown fox jumps over the lazy dog.
	
	|| table cell 1 || table _
	cell 2 || table cell 3 ||
	


*  The quick brown fox jumps over the lazy dog.

*  The quick brown
fox jumps over
the lazy dog.

*  The quick brown fox jumps over the lazy dog.
 | table cell 1 | table
 | ------------ | -----
cell 2 | table cell 3 |

