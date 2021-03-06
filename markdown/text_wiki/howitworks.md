
Text_Wiki works in two stages: parse, and render.  (The ''[transform()](MethodTransform)'' method does them in sequence for you so you don't need to issue two commands -- although you can if you want to.)

##  Parse

When parsing, Text_Wiki makes a copy of the source text.  It then applies "rules" (class files of regular expressions and processing commands) and looks for specific structured text (markup) in the source.

When a rule finds matching markup, it replaces the matching text with a "delimited token" and creates an entry in the ''$tokens'' property array.  The delimiters are the ''\xFF'' character (ASCII 255) and surround a token number in the source text.  The token number refers to the Text_Wiki ''$tokens'' array key, which contains information about the rule that placed the token and information about how to render output.

As Text_Wiki applies the various rules to the source text, more and more of the original text is replaced with delimited tokens, and more related elements are placed in the ''$tokens'' array.  By the end of the rule set, the source text is filled with delimited tokens; whatever remains is "literal" text to be output as it is at render-time.

##  Render

Rendering is the obverse of parsing, and happens in three substages.

First, Text_Wiki loads a format object (e.g., Xhtml), and runs the pre-render method for the given format.

Next, Text_Wiki looks at the ''$tokens'' array, genrates output for the format based on the rule that created each token, and replaces the delimited token number in the source with the output from its respective render class.

Finally, Text_Wiki runs the post-render method for the given format, and returns the newly-formatted text.

##  Multiple Output Formats

Text_Wiki converts wiki text into an intermediate format (the ''$tokens'' array) instead of converting it directly into XHTML.  This means that, if an appropriate rendering method exists, the intermediate ''$tokens'' array can be used to create not only XHTML but any form of output, such as LaTeX, RTF, PDF, or DocBook.

