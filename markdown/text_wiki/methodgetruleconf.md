
`<html>``<div style="text-align: center;">``</html>``<html>``<span style="color: red;">``</html>`DEPRECATED`<html>``</span>``</html>``<html>``</div>``</html>`

#  ''getRuleConf()''

''mixed **getRuleConf** (string **rule key** [, string **config key** default null])''

Get the value of a rule configuration.  By default, returns the entire configuration array for the rule; alternatively, if you specify a configuration key as the second parameter, returns only the value for that configuration key.

`<php>`

** [snip] create a Text_Wiki object called $wiki

** get the entire configuration array for the wikilink rule
$conf = $wiki->getRuleConf('wikilink');

// get the 'view_url' value in the wikilink configuration array
$view_url = $wiki->getRuleConf('wikilink', 'view_url');
`</php>`

