<table border="0" cellpadding="4" cellspacing="5">
  <tr>
    <td><img src="https://jaygilford.com/vQmod_Logo.png" alt="vQmod - virtual file modification system" width="400" height="113" /></td>

  </tr>
</table>

##[Download Now](https://github.com/vqmod/vqmod/releases)

<h4><u><strong>Looking for Install/Upgrade help? Click the Install link on the sidebar to the right.</strong></u></h3>


<h3><u><strong>Welcome to vQmod™</strong></u></h3>

"vQmod™" (aka Virtual Quick Mod) is an override system designed to avoid having to change core files. The concept is quite simple... Instead of making changes to the core files directly, the changes are created as xml search/replace script files. These script files are parsed during page load as each "source" core file is loaded with the "include" or "require" php functions. The source is then patched with the script file changes, and saved to a temp file. That temp file is then substituted for the original during execution. The original source file is never altered. This results in a "virtual" change to the core during execution without any actual modification to the core files.

See wiki links for additional information, usage, and syntax


<h3><u><strong>Features</strong></u></h3>
<ul>
    <li>No actual code changes are made. All changes are "virtual", hence the name.</li>
    <li>Modifications are stored in their own files and applied "on-the-fly" at runtime</li>
    <li>Instant Single file "plug-n-play". Add the file to apply the mod, remove the file to remove the mod.</li>
    <li>No worries about losing custom core changes during upgrades</li>
    <li>Multiple modifications can be made to the same file without conflict</li>
    <li>Easily update or enhance customizations without having to edit any code</li>
    <li>Full visual of the actual changes taking place in the generated temp files for debugging</li>
    <li>Fails gracefully back to the original sourcefile if there is an error</li>
    <li>Exceptional logging option to track every change made</li>
    <li>Only need to modify the index.php file to add the vQmod code one time.</li>
    <li>Simple structured xml format. (See readme for full breakdown of xml syntax)</li>
    <li>Multiple options for find/replace, regex, positions, offsets, indexing, error handling, and more!</li>
</ul>
<p>This system can be used for any php script, forum, shopping cart, cms, etc. Anywhere custom modifications are made for reuse. The logging option is invaluable for debugging understanding exactly what is happening.<br />
After the initial class load, the mod can actually use a script to mod itself into other core files that do the actual includes for other mods. This is the first and only known method to allow the ability to test multiple mods without actually changing files.</p>

<h3><u><strong>Who can use it?</strong></u></h3>
<p>It was initially designed in php using the OpenCart project, but it is not limited to OpenCart, nor is the concept limited to php. The class was designed to be generic enough to work with any platform. The only thing to figure is how all the include/require points of the platform so that you can make the necessary changes to install vQmod. vQmod works on an assumption that the index.php calls other controller files to load the includes, or does the includes itself. This is aimed at controller based designs (MVC, CRUD, etc). We are working on expanding from OpenCart to other platforms (phpbb, cmsmadesimple, etc)</p>

<h3><u><strong>What about performance?</strong></u></h3>
<p>Performance has been my concern from the first idea of this project. But the way the code is designed has reduced any effect on performance. We've got over 30 vQmod scripts on our test sites with page times and have seen absolutely no performance change when enabled or disabled. Of course any script that causes a change to db queries or has code that takes longer will be a factor but that would not be a vQmod performance issue. When the actual source files are parsed, only the files that have changes need to parse the xml scripts. Additionally, multiple performance tips and tweaks have been added as well as an optional "useCache" feature that allows you reload the changes made already from the vqcache files. All in all, performance suprisingly does not appear to be a factor at all.</p>

<h3><u><strong>Get Started Now</strong></u></h3>
  * [http://code.google.com/p/vqmod/wiki/Install_OpenCart Install]
  * [http://code.google.com/p/vqmod/wiki/Scripting Scripting]
  * [http://code.google.com/p/vqmod/wiki/Examples Examples]