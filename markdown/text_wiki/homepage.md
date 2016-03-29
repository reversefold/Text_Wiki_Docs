
`<html>``<div style="text-align: center;">``</html>`The documentation on this site refers to version 0.22.0 alpha, released 2004-09-19, but the most recent version is 0.24.0 beta, released 2005-01-30.  The differences between the two are negligible.`<html>``</div>``</html>`

##  What Text_Wiki Does

The ''Text_Wiki'' package allows you to transform text structured using [Wiki](http://c2.com/cgi/wiki) rules into any defined target output format, such as XHTML, RTF, LaTeX, and so on.

**Note:** The current release only supports XHTML and plain-text output.  RTF, LaTeX, DocBook, and so on will be added as the codebase stabilizes and matures.
''Text_Wiki'' achieves this level of flexibility by using one class for each part of the transformation process:


*  one class for parsing each markup rule (e.g., bold, code, wikilink, etc)

*  one class for rendering each general format (e.g., XHTML, DocBook, RTC, etc)

*  one class for rendering each rule in each format
''Text_Wiki'' comes with its own set of markup rules (see the [SamplePage](SamplePage)), but you can write any rules you like to match whatever style you're used to.  ''Text_Wiki'' draws its default rules from a number of codebases, most notably [WikkiTikkiTavi](http://tavi.sourceforge.net) and [coWiki](http://develnet.org/); while no code has been directly copied from those codebases, they were indispensible in learning how to process Wiki text.

##  What Text_Wiki Does Not Do

The ''Text_Wiki'' package does not implement storage, saving, editing, diffs, page counts, and so on.  Those functions are more properly the domain of a full Wiki application and environment, which is outside the stated ''Text_Wiki'' goals (i.e., to transform Wiki text according to defined rules for a target output format).  You may wish to examine [Yawiki](http://wiki.ciaweb.net/yawiki/index.php?wiki=Yawiki) if you need a full Wiki system and not just a wiki parser.

