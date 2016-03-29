 About This Rule Parse Configuration Keys Render Configuration Keys Description Alignment Headers Row Spans
##  About This Rule

 | **Name**   | table               | 
 | --------   | -----               | 
 | **Type**   | non-capturing block | 
 | **Syntax** | `<nowiki>`            |  | `</nowiki>` at the beginning of a line, with `<nowiki>` |  | `</nowiki>` to separate cells, and `<nowiki>` |  | `</nowiki>` at the end of the line, with optional alignment character (`<'' for left, ''='' for center, ''>` for right) **or** a tilde to mark a header cell | 

##  Parse Configuration Keys

None.

##  Render Configuration Keys

 | **Format** | **Key**       | **Type** | **Description**                           | 
 | ---------- | -------       | -------- | ---------------                           | 
 | ''Xhtml''  | ''css_table'' | string   | The CSS class to use for the `<table>` tag. | 
 | ''Xhtml''  | ''css_tr''    | string   | The CSS class to use for the `<tr>` tag.    | 
 | ''Xhtml''  | ''css_th''    | string   | The CSS class to use for the `<th>` tag.    | 
 | ''Xhtml''  | ''css_td''    | string   | The CSS class to use for the `<td>` tag.    | 

##  Description

This will let you create tables in your source text.  The easiest way to describe it is to show an example:

	
	
	|| Cell 1 || Cell 2 ||
	|| Cell 3 || Cell 4 ||

 | Cell 1 | Cell 2 | 
 | ------ | ------ | 
 | Cell 3 | Cell 4 | 

If you include a blank line between table lines, you will start a new table.

	
	
	|| cell 1 || cell 2 ||
	
	|| cell 3 || cell 4 ||

 | cell 1 | cell 2 | 
 | ------ | ------ | 

 | cell 3 | cell 4 | 
 | ------ | ------ | 

###  Alignment

You can align the contents of a cell by including a `<'', ''='', or ''>` character after the ''||'' marker.

	
	
	||`< left ||= center ||>` right ||
	|| The quick brown || fox jumps over || the lazy dog. ||

 | left            | center         | right         | 
 | ----            | ------         | -----         | 
 | The quick brown | fox jumps over | the lazy dog. | 

###  Headers

You can mark a cell as a `<th>` cell by using a ~ character after the || marker.

	
	
	||~ header 1 ||~ header 2 ||
	|| data 1    || data 2    ||

 | header 1 | header 2 |
 | -------- | ----------
 | data 1   | data 2     | 

###  Row Spans

To span multiple rows, use multiple || markers.

	
	
	|| cell 1 || cell 2 || cell 3 || cell 4 ||
	|||| span 2 cols || third || fourth ||
	|| first |||||| span 3 cols ||

 | cell 1      | cell 2      | cell 3 | cell 4 | 
 | ------      | ------      | ------ | ------ | 
 | span 2 cols |             | third  | fourth | 
 | first       | span 3 cols |        |        | 

