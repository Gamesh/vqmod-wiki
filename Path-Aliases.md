#Path aliases

vQmod lets you use aliases to substitute the more commonly know path with your own renamed path. The most example of this is when you rename your opencart "admin" folder to something else. Since all the xml scripts reference the "admin/" path, this can cause your scripts to fail. 

So we've included a file called "pathReplaces.php". You can edit this file and create an alias, or shortcut, from the normal "admin" to "backend" or whatever you call it. There is an example at the top of that file on how to add it. This prevents you from having to manually edit all your xml files to change the path.

Here is an example that redirects the "admin" folder to a "backend" folder.

	// START REPLACES //
	$replaces[] = array('~^admin\b~', 'backend'); // This replaces the admin folder name to backend
	// END REPLACES //

These are regex replaces so be sure you keep the additional characters like ~ and ^ as those are important for proper name matching.

Available from version 2.3.0 onwards