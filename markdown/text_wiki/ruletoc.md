 About This Rule Parse Configuration Keys Render Configuration Keys Description
##  About This Rule

 | **Name**   | toc                                      | 
 | --------   | ---                                      | 
 | **Type**   | macro                                    | 
 | **Syntax** | `<nowiki>`[`</nowiki>`toc](`</nowiki>`toc)'' | 

##  Parse Configuration Keys

None.

##  Render Configuration Keys

 | **Format** | **Key**      | **Type** | **Description**                                                                                              | 
 | ---------- | -------      | -------- | ---------------                                                                                              | 
 | ''Xhtml''  | ''div_id''   | string   | The ID attribute to use for the `<div>` tag that wraps the entire table of contents listing; default to 'toc'. | 
 | ''Xhtml''  | ''css_list'' | string   | The CSS class to use for the `<div>` tag that wraps the entire table of contents listing.                      | 
 | ''Xhtml''  | ''css_item'' | string   | The CSS class to use for the `<div>` tag that wraps each individual entry in the list.                         | 
 | ''Xhtml''  | ''title''    | string   | Raw XHTML to place above the table of contents list; defaults to `<strong>`Table of Contents`</strong>`.       | 

##  Description

Looks through all the heading elements in the source text and creates a table of contents from them; each table of contents entry is linked to the appropriate heading, so you can click on it to go to the heading.

