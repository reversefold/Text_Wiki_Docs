 About This Rule Parse Configuration Keys Render Configuration Keys Description
##  About This Rule

 | **Name**   | delimiter | 
 | --------   | --------- | 
 | **Type**   | filter    | 
 | **Syntax** | n/a       | 

##  Parse Configuration Keys

None.

##  Render Configuration Keys

None.

##  Description

The Text_Wiki engine uses a delimiting character to mark replacement tokens in the parsed source text.  By default, the delimiter is ASCII character number 255, also known as ''\xFF'' or ''chr(255)''.

This rule removes all instances of the delimiter character from the source text and replaces them with delimited tokens; this keeps Text_Wiki from becoming confused by delimiters already present in the source text which are not token markers.

