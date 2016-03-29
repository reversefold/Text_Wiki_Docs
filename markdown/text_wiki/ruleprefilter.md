 About This Rule Parse Configuration Keys Render Configuration Keys Description
##  About This Rule

 | **Name**   | prefilter | 
 | --------   | --------- | 
 | **Type**   | filter    | 
 | **Syntax** | n/a       | 

##  Parse Configuration Keys

None.

##  Render Configuration Keys

None.

##  Description

The 'prefilter' rule does two things:


*  Converts Mac and Dos line endings to Unix line endings

*  Takes lines ending in \ and concatenates them with the next line.
For example, this text ...

	
	
	Line 1
	
	Line 2 \ 
	Line 3
	
	Line 4

will become:

	
	
	Line 1
	
	Line 2 Line 3
	
	Line 4

If you want to end a line in a backslash but do **not** want it concatenated to the next line, put a space after the backslash.

If you want to end a line in a backslash **and** concatenate it to the next line, use two backslashes.

