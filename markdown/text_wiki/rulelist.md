 About This Rule Parse Configuration Keys Render Configuration Keys Description
##  About This Rule

 | **Name**   | list                                                                                                                            | 
 | --------   | ----                                                                                                                            | 
 | **Type**   | non-capturing block                                                                                                             | 
 | **Syntax** | Zero or more spaces at the beginning of a line, followed by ''*'' or ''#'', followed by a space, followed by the list item text | 

##  Parse Configuration Keys

None.

##  Render Configuration Keys

 | **Format** | **Key**       | **Type** | **Description**                             | 
 | ---------- | -------       | -------- | ---------------                             | 
 | ''Xhtml''  | ''css_ol''    | string   | The CSS class for `<ol>` tags.                | 
 | ''Xhtml''  | ''css_ol_li'' | string   | The CSS class for `<li>` tags in `<ol>` blocks. | 
 | ''Xhtml''  | ''css_ul''    | string   | The CSS class for `<ul>` tags.                | 
 | ''Xhtml''  | ''css_ul_li'' | string   | The CSS class for `<li>` tags in `<ul>` blocks. | 

##  Description

Use this to create ordered lists with a ''#'' character, or unordered lists with a ''*'' marker.

	
	
	Numbered list:
	
	# one
	# two
	# three
	
	Bulleted list:
	

	* four
	* five
	* six

Numbered list:

 1.  one
 2.  two
 3.  three
Bulleted list:


*  four

*  five

*  six----
Adding spaces before the marking indents the list items.  You can mix ordered and unordered lists.

	
	
	# Main 1

	 * subitem 1
	 * subitem 2
	# Main 2
	 # Main 2a

	  * sub-subitem
	 # Main 2b

	  * sub-subitem
	# Main 3

 1.  Main 1

    * subitem 1
    * subitem 2
 2.  Main 2
    - Main 2a

      * sub-subitem
    - Main 2b

      * sub-subitem
 3.  Main 3
