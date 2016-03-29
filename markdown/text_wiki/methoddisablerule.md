
''void **disableRule** (string **rule name**)''

Disables an existing rule in the rule set so that the parser will use it.  Does not delete the rule from the set.

`<php>`

** [snip] create a Text_Wiki object called $wiki
** disable the HTML rule in the rule set
$wiki->disableRule('html');
`</php>`

