
''array **getPath** ([string **path type**])''

Gets the list of directories that Text_Wiki searches for parse and render rules.  The order listed by getPath() is the order in which they are searched.

	:::php
	
	$wiki =& new Text_Wiki();
	
	// get all search paths
	$all_dirs = $wiki->getPath();
	
	// get only the search paths for parse rules
	$parse_dirs = $wiki->getPath('parse');

