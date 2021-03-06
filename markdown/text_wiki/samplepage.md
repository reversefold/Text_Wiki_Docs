 General Notes Inline Formatting Literal Text Headings Level 3 HeadingLevel 4 Heading Level 5 HeadingLevel 6 Heading Table of Contents Horizontal Rules Lists Bullet Lists Numbered Lists Mixing Bullet and Number List Items Definition Lists Block Quotes Links and Images Wiki Links Interwiki Links URLs Images Code Blocks Tables----
##  General Notes

The markup described on this page is for the default ''Text_Wiki'' rules; it is a combination of the [WikkTikkiTavi](http://tavi.sourceforge.net) and [coWiki](http://develnet.org/) markup styles.

All text is entered as plain text, and will be converted to HTML entities as necessary.  This means that `<'', ''>`, ''&'', and so on are converted for you (except in special situations where the characters are Wiki markup; Text_Wiki is generally smart enough to know when to convert and when not to).

Just hit "return" twice to make a paragraph break.  If you want to keep the same logical line but have to split it across two physical lines (such as when your editor only shows a certain number of characters per line), end the line with a backslash ''\'' and hit return once.  This will cause the two lines to be joined on display, and the backslash will not show.  (If you end a line with a backslash and a tab or space, it will *not* be joined with the next line, and the backslash will be printed.)
----
##  Inline Formatting

 | `<nowiki>`//emphasis text//`</nowiki>`                    | **emphasis text**                                | 
 | --------------------------------------                    | -----------------                                | 
 | `<nowiki>`strong text`</nowiki>`                      | **strong text**                                  | 
 | `<nowiki>`//**emphasis and strong**//`</nowiki>`          | ****emphasis and strong****                      | 
 | `<nowiki>`{{teletype text}}`</nowiki>`                    | ''teletype text''                                | 
 | `<nowiki>`@@--- delete text +++ insert text @@`</nowiki>` | `<del>` delete text `</del>``<ins>` insert text `</ins>` | 
 | `<nowiki>`@@--- delete only @@`</nowiki>`                 | `<del>` delete only `</del>`                         | 
 | `<nowiki>`@@+++ insert only @@`</nowiki>`                 | `<ins>` insert only `</ins>`                         | 
----
##  Literal Text

If you don't want Text_Wiki to parse some text, enclose it in two backticks (not single-quotes).

	
	
	
	This *text* gets **parsed**.
	
	``This *text* does not get **parsed**.``
	

This **text** gets **parsed**.

`<nowiki>`This *text* does not get **parsed**.`</nowiki>`
----
##  Headings

You can make various levels of heading by putting equals-signs before and after the text (all on its own line):

	
	
	
	+++  Level 3 Heading
	
	++++ Level 4 Heading
	
	+++++  Level 5 Heading
	
	++++++ Level 6 Heading

###  Level 3 Heading

#### Level 4 Heading
#####  Level 5 Heading

######  Level 6 Heading----
##  Table of Contents

To create a list of every heading, with a link to that heading, put a table of contents tag on its own line.

	
	
	[[toc]]
	`</code>`----
	##   Horizontal Rules
	Use four dashes (`<nowiki>`----`</nowiki>`) to create a horizontal rule.
	----
	##   Lists
	###   Bullet Lists
	You can create bullet lists by starting a paragraph with one or more asterisks.
	`<code>`
	

	* Bullet one
	 * Sub-bullet


*  Bullet one
    * Sub-bullet
###  Numbered Lists

Similarly, you can create numbered lists by starting a paragraph with one or more hashes.

	
	
	# Numero uno
	# Number two
	 # Sub-item

 1.  Numero uno
 2.  Number two
    - Sub-item
###  Mixing Bullet and Number List Items

You can mix and match bullet and number lists:

	
	
	# Number one

	 * Bullet
	 * Bullet
	# Number two

	 * Bullet
	 * Bullet
	  * Sub-bullet
	   # Sub-sub-number
	   # Sub-sub-number
	# Number three

	 * Bullet
	 * Bullet

 1.  Number one

    * Bullet
    * Bullet
 2.  Number two

    * Bullet
    * Bullet
      * Sub-bullet
        - Sub-sub-number
        - Sub-sub-number
 3.  Number three

    * Bullet
    * Bullet
###  Definition Lists

You can create a definition (description) list with the following syntax:

	
	
	: Item 1 : Something
	: Item 2 : Something else
	`</code>`Item 1SomethingItem 2Something else----
	##   Block Quotes
	You can mark a blockquote by starting a line with one or more '>' characters, followed by a space and the text to be quoted.
	`<code>`
	
	This is normal text here.
	
	> Indent me! The quick brown fox jumps over the lazy dog. \ 
	Now this the time for all good men to come to the aid of \ 
	their country. Notice how we can continue the block-quote \ 
	in the same "paragraph" by using a backslash at the end of \ 
	the line.
	>
	> Another block, leading to...
	>> Second level of indenting.  This second is indented even \ 
	more than the previous one.
	
	Back to normal text.

This is normal text here.
Indent me! The quick brown fox jumps over the lazy dog. Now this the time for all good men to come to the aid of their country. Notice how we can continue the block-quote in the same "paragraph" by using a backslash at the end of the line.
Another block, leading to...
Second level of indenting.  This second is indented even more than the previous one.
Back to normal text.
----
##  Links and Images

###  Wiki Links
[SmashWordsTogether](SmashWordsTogether) to create a page link.

You can force a [WikiPage](WikiPage) name **not** to be clickable by putting an exclamation mark in front of it.

	
	
	WikiPage !WikiPage

[WikiPage](WikiPage) WikiPage

You can create a "described" or "labeled" link to a wiki page by putting the page name in brackets, followed by some text.

	
	
	[WikiPage Descriptive text for the link.]

[Descriptive text for the link.](WikiPage)

**Note:** existing wiki pages must be in the [wikilink](RuleWikilink) ''pages'' configuration,  and the [wikilink](RuleWikilink) ''view_url'' configuration value must be set for the linking to work.
###  Interwiki Links

Interwiki links are links to pages on other Wiki sites. Type the `<nowiki>`SiteName:PageName`</nowiki>` like this:


*  [MeatBall:RecentChanges](MeatBall>RecentChanges)

*  [Advogato:proj/WikkiTikkiTavi](Advogato>proj/WikkiTikkiTavi)

*  [Wiki:WorseIsBetter](Wiki>WorseIsBetter)**Note:** the interwiki site must be in the [interwiki](RuleInterwiki) ''sites'' configuration array.
###  URLs

Create a remote link simply by typing its URL: [http://ciaweb.net](http://ciaweb.net).

If you like, enclose it in brackets to create a numbered reference and avoid cluttering the page; `<nowiki>`[http://ciaweb.net/free/]`</nowiki>` becomes [1](http://ciaweb.net/free/).

Or you can have a described-reference instead of a numbered reference:

	
	
	[http://pear.php.net PEAR]

[PEAR](http://pear.php.net)

###  Images

You can put a picture in a page by typing the URL to the picture (it must end in gif, jpg, or png).

	
	
	http://c2.com/sig/wiki.gif


[http://c2.com/sig/wiki.gif](http://c2.com/sig/wiki.gif)

You can use the described-reference URL markup to give the image an ALT tag:

	
	
	[http://phpsavant.com/etc/fester.jpg Fester]


[Fester](http://phpsavant.com/etc/fester.jpg)
----
##  Code Blocks

Create code blocks by using ''`...`'' tags (each on its own line).

	
	
	This is an example code block!

To create PHP blocks that get automatically colorized when you use PHP tags, simply surround the code with ''`...`{type="php"}'' tags (the tags themselves should each be on their own lines, and no need for the `<?php ... ?>` tags).

	
	
	 `<code type="php">`
	 // Set up the wiki options
	 $options = array();
	 $options['view_url'] = "index.php?page=";
	
	 // load the text for the requested page
	 $text = implode('', file($page . '.wiki.txt'));
	
	 // create a Wiki objext with the loaded options
	 $wiki = new Text_Wiki($options);
	
	 // transform the wiki text.
	 echo $wiki->transform($text);

`</code>``<code php>`

// Set up the wiki options
$options = array();
$options['view_url'] = "index.php?page=";

// load the text for the requested page
$text = implode('', file($page . '.wiki.txt'));

// create a Wiki objext with the loaded options
$wiki = new Text_Wiki($options);

// transform the wiki text.
echo $wiki->transform($text);
`</code>`----
##  Tables

You can create tables using pairs of vertical bars:

	
	
	|| cell one || cell two ||
	|||| big ol' line ||
	|| cell four || cell five ||
	|| cell six || here's a very long cell ||

 | cell one     | cell two                | 
 | --------     | --------                | 
 | big ol' line |                         | 
 | cell four    | cell five               | 
 | cell six     | here's a very long cell | 

	
	
	|| lines must start and end || with double vertical bars || nothing ||
	|| cells are separated by || double vertical bars || nothing ||
	|||| you can span multiple columns by || starting each cell ||
	|| with extra cell |||| separators ||
	|||||| but perhaps an example is the easiest way to see ||

 | lines must start and end                         | with double vertical bars | nothing            | 
 | ------------------------                         | ------------------------- | -------            | 
 | cells are separated by                           | double vertical bars      | nothing            | 
 | you can span multiple columns by                 |                           | starting each cell | 
 | with extra cell                                  | separators                |                    | 
 | but perhaps an example is the easiest way to see |                           |                    | 

