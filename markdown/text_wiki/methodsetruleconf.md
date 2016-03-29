
`<html>``<div style="text-align: center;">``</html>``<html>``<span style="color: red;">``</html>`DEPRECATED`<html>``</span>``</html>``<html>``</div>``</html>`

#  ''setRuleConf()''

''void **setRuleConf** (string **rule name**, array **config array**)''

-- or --

''void **setRuleConf** (string **rule name**, string **config key**, mixed **config value**)''

Set a configuration value for a Text_Wiki rule.  You can either specify the entire configuration array, or specify a key and value for the configuration.

Here's how to set the entire configuration array at once:

`<php>`

** [snip] create a Text_Wiki object called $wiki

** set up a configuration array
$conf = array(
    'pages' => array('[HomePage](HomePage)', '[AnotherPage](AnotherPage)', '[SomeOtherPage](SomeOtherPage)'),
    'view_url' => '[http://example.php/view.php?page=](http://example.php/view.php?page=)',
    'new_url' => '[http://example.php/new.php?page=](http://example.php/new.php?page=)',
    'new_text' => '?'
);

** configure a rule; this will overwrite
** the entire previous configuration array
$wiki->setRuleConf('wikilink', $conf);
`</php>`

Here's how to do the same thing, one key at a time.  This has the benefit of only overwriting that specific configuration key, not the entire configuration array.

`<php>`

** [snip] create a Text_Wiki object called $wiki

** set the wikilink 'pages' config value
$wiki->setRuleConf(
    'wikilink',
    'pages',
    array(
        '[HomePage](HomePage)', '[AnotherPage](AnotherPage)', '[SomeOtherPage](SomeOtherPage)'
    )
);

** set the wikilink 'view_url' config value
$wiki->setRuleConf('wikilink', 'view_url', '[http://example.php/view.php?page=](http://example.php/view.php?page=)');

** set the wikilink 'new_url' config value
$wiki->setRuleConf('wikilink', 'new_url', '[http://example.php/new.php?page=](http://example.php/new.php?page=)',

// set the wikilink 'new_text' config value
$wiki->setRuleConf('wikilink', 'new_text', '?');
`</php>`

