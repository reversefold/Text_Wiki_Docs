 What Is A Rule? Kinds of Rules Rule Order Rule Configuration Enable/Disable Rules
##  What Is A Rule?

A Text_Wiki "rule" is a combination of class files that interprets Wiki-style markup in the source text and transforms it into some other form of markup or output.  Each "rule" consists of one parsing class, to convert a specific kind of Wiki markup into an internal format, and one render class per output format.

For example, the "bold" rule has a parsing class (Text_Wiki_Parse_Bold) along with a rendering class for XHTML (Text_Wiki_Render_Xhtml_Bold) and a rendering class for plain text (Text_Wiki_Render_Plain_Bold).  As more output formats are added to Text_Wiki, each rule will have a new rendering class for the new format.

There is a similar combination of class files for each Text_Wiki rule: italic text, wiki links, headings, and so on.

##  Kinds of Rules

There are five general kinds of rules in Text_Wiki; these are ways to think about how the rule operates on the source text, not classes or methods within Text_Wiki.

**Filter**This kind of rule filters the entire source text at one time.  Filters do not use markup of any sort in the source text; they are applied to the entire source.  The 'entities' and 'prefilter' rules are filter rules.**Capturing Blocks**These rules "capture" one or more matching blocks of source text lines and remove them from further processing by the remaining rules.  The 'html' and 'code' rules are capturing-block rules.**Non-Capturing Blocks**These rules find one or more matching blocks of source text lines and mark the beginning and end of the block, but leave the lines themselves in place so that they can continue to be processed by the remaining rules.  The 'paragraph' and 'list' rules are non-capturing block rules.**Inline**The inline rules mark the beginning and end of wiki markup on a single line.  The 'bold' and 'superscript' rules are inline rules.**Macro**Macro rules are mini-scripts that act on the text or tokens within Text_Wiki and may or may not allow to pass options within the markup (most do).  Macros can be very powerful and/or dangerous depending on your operating environment.  The 'embed' and 'phplookup' rules are macros.
##  Rule Order

The order in which the rules are processed during parsing matters a great deal.  Thus, processing the 'wikilink' rule before the 'url' rule may result in undesired or corrupted output.

The default rule set for Text_Wiki is parsed in the following order; rendering happens in the same order after parsing is complete.

 | **Name**                           | **Kind**            | **Description **                                                                                                  | 
 | --------                           | --------            | ----------------                                                                                                  | 
 | [prefilter](RulePrefilter)         | filter              | Convert line endings and concatentate lines ending with a backslash `<nowiki>`\`</nowiki>`                        | 
 | [delimiter](RuleDelimiter)         | filter              | Remove all instances of `<nowiki>`\xFF`</nowiki>`, the delimiter used to mark tokens in the processed source text | 
 | [code](RuleCode)                   | capturing block     | Generic code example                                                                                              | 
 | [html](RuleHtml)                   | capturing block     | HTML markup                                                                                                       | 
 | [raw](RuleRaw)                     | capturing block     | Any text that should not be processed by remaining Text_Wiki rules                                                | 
 | [include](RuleInclude)             | macro               | Include a script whose output should be processed by remaining Text_Wiki rules                                    | 
 | [embed](RuleEmbed)                 | macro               | Include a script whose output should be displayed (but not parsed)                                                | 
 | [anchor](RuleAnchor)               | capturing block     | Add an anchor name (as a target) to the page.                                                                     | 
 | [heading](RuleHeading)             | non-capturing block | Section headers                                                                                                   | 
 | [toc](RuleToc)                     | macro               | Display a table of contents built from all headers in the source text                                             | 
 | [horiz](RuleHoriz)                 | capturing block     | Horizontal line bars                                                                                              | 
 | [break](RuleBreak)                 | inline              | Explicit line breaks                                                                                              | 
 | [blockquote](RuleBlockquote)       | non-capturing block | Block-quoted text                                                                                                 | 
 | [list](RuleList)                   | non-capturing block | Ordered and unordered lists                                                                                       | 
 | [deflist](RuleDeflist)             | non-capturing block | Definition lists                                                                                                  | 
 | [table](RuleTable)                 | non-capturing block | Tables                                                                                                            | 
 | [image](RuleImage)                 | macro               | Display an image                                                                                                  | 
 | [phplookup](RulePhplookup)         | macro               | Display a link the PHP manual                                                                                     | 
 | [center](RuleCenter)               | non-capturing block | Marks a line to be centered                                                                                       | 
 | [newline](RuleNewline)             | inline              | Single newlines in paragraphs and block-quotes are converted to line breaks                                       | 
 | [paragraph](RuleParagraph)         | non-capturing block | Marks a line as a semantic paragraph                                                                              | 
 | [url](RuleUrl)                     | inline              | Display a link to a URL                                                                                           | 
 | [freelink](RuleFreelink)           | inline              | Display a link to a local wiki page in free-link format                                                           | 
 | [interwiki](RuleInterwiki)         | inline              | Display a link to an Interwiki site                                                                               | 
 | [wikilink](RuleWikilink)           | inline              | Display a link to a local wiki page in normal wiki-link format                                                    | 
 | [colortext](RuleColortext)         | inline              | Display colored text                                                                                              | 
 | [strong](RuleStrong)               | inline              | Semantic strong (bold) text                                                                                       | 
 | [bold](RuleBold)                   | inline              | Bold text                                                                                                         | 
 | [emphasis](RuleEmphasis)           | inline              | Semantic emphasized (italic) text                                                                                 | 
 | [italic](RuleItalic)               | inline              | Italic text                                                                                                       | 
 | [tt](RuleTt)                       | inline              | Teletype (monospaced) text                                                                                        | 
 | [superscript](RuleSuperscript)     | inline              | Superscripted text                                                                                                | 
 | [revise](RuleRevise)               | inline              | Inserted and deleted (revised) text                                                                               | 
 | [tighten](RuleTighten)             | filter              | 3 or more newlines in a row are reduced to 2 newlines                                                             | 
 | [translatehtml](RuleTranslatehtml) | filter              | Translate HTML entities in the source                                                                             | 

##  Rule Configuration

Because processing of a rule happens in two steps, one for parsing and one for rendering, there are two sets of configuration options for each rule.  Frankly, there is not much configuration needed at parsing time, but sometimes it is necessary.  Configuration for the rendering of a rule is generally more important.

To set the configuration for rule parsing on all source text, use [setParseConf()](MethodSetParseConf).

To set the configuration for rule rendering for a specific output format, use [setRenderConf()](MethodSetRenderConf).

Rule configuration values, if any, are described on the individual rule pages.

##  Enable/Disable Rules

If you want to disable a rule, use the ''disableRule()'' method. To re-enable a rule, use ''enableRule()''.  This will not change the order of processing.

	:::php
	
	// [snip] instantiate a Text_Wiki object ($wiki).
	
	// now disable the HTML, embed, and include rules.
	$wiki->disableRule('html');
	$wiki->disableRule('embed');
	$wiki->disableRule('include');
	
	// turn the 'html' rule back on
	$wiki->enableRule('html');

