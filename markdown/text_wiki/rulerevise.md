 About This Rule Parse Configuration Keys Render Configuration Keys Description
##  About This Rule

 | **Name**   | revise                                                                  | 
 | --------   | ------                                                                  | 
 | **Type**   | inline                                                                  | 
 | **Syntax** | `<nowiki>`@@`</nowiki>`---**delete this text**+++**insert this text**@@'' | 

##  Parse Configuration Keys

None.

##  Render Configuration Keys

 | **Format** | **Key**     | **Type** | **Description**                  | 
 | ---------- | -------     | -------- | ---------------                  | 
 | ''Xhtml''  | ''css_del'' | string   | The CSS class for the `<del>` tag. | 
 | ''Xhtml''  | ''css_ins'' | string   | The CSS class for the `<ins>` tag. | 

##  Description

Use this rule to mark revisions in the source text without actually deleting anything.

	
	
	@@---Please delete these comments.+++Add these comments instead.@@
	
	@@---Only delete this.@@
	
	@@+++Only add this.@@

`<del>`Please delete these comments.`</del>``<ins>`Add these comments instead.`</ins>`

`<del>`Only delete this.`</del>`

`<ins>`Only add this.`</ins>`

