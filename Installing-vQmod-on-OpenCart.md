#How to install vQmod on OpenCart


##New Install Video Tutorial (OpenCart)
[Youtube Install Video](https://www.youtube.com/watch?v=ezS1jWoMmjc)

##Installing on OpenCart

vQmod works with OpenCart 1.4.x, 1.5.x, and OpenCart 2.0.x

###How to install using Autoinstaller

  1 Download the latest version that has "opencart" in the title from the download area. 

  2. Using FTP, upload the "vqmod" folder from the zip to the root of your opencart store.

  3. Be sure the vqmod folder and the vqmod/vqcache folders are writable (either 755 or 777). 
    * Also be sure index.php and admin/index.php are writable.
      * If not sure which you need, first try 755. 
      * If you get errors about permissions, then try 777.

NOTE: 777 permissions are dangerous and should only be used as a last resort. If your hosting requires this, consult your hosting to let them know this shouldn't be necessary

  4. Goto http://www.yoursite.com/vqmod/install 

  5. You should get a success message. If not, check permissions above and try again

  6. Load your store homepage and verify it works.

  7. Using FTP, verify that there are new "vq" files in the "vqmod/vqcache" folder.

  8. If yes, then you are ready to start downloading or creating vQmod scripts, otherwise ask for assistance.

Done!


  * *DO NOT DELETE THE INSTALL FOLDER!*
  * *YOU MUST RUN THE INSTALLER EVERY TIME YOU UPGRADE OPENCART!!*
  * *THERE IS NO DANGER OF RE-RUNNING THE INSTALLER!*


###How to install Manually

  1 Download the latest version that has "opencart" in the title from 

  2. Using FTP, upload the "vqmod" folder from the zip to the root of your opencart store.

  3. Be sure the vqmod folder and the vqmod/vqcache folders are writable (either 755 or 777). 
    * Also be sure index.php and admin/index.php are writable.
      * If not sure which you need, first try 755. 
      * If you get errors about permissions, then try 777.
  
  4. Edit your *index.php* file
  
  5. FIND:

	// Startup
	require_once(DIR_SYSTEM . 'startup.php');
	
	// Application Classes
	require_once(DIR_SYSTEM . 'library/customer.php');
	require_once(DIR_SYSTEM . 'library/currency.php');
	require_once(DIR_SYSTEM . 'library/tax.php');
	require_once(DIR_SYSTEM . 'library/weight.php');
	require_once(DIR_SYSTEM . 'library/length.php');
	require_once(DIR_SYSTEM . 'library/cart.php');
	require_once(DIR_SYSTEM . 'library/affiliate.php');

  6. REPLACE WITH:

	// vQmod
	require_once('./vqmod/vqmod.php');
	VQMod::bootup();
	
	// VQMODDED Startup
	require_once(VQMod::modCheck(DIR_SYSTEM . 'startup.php'));
	
	// Application Classes
	require_once(VQMod::modCheck(DIR_SYSTEM . 'library/customer.php'));
	require_once(VQMod::modCheck(DIR_SYSTEM . 'library/currency.php'));
	require_once(VQMod::modCheck(DIR_SYSTEM . 'library/tax.php'));
	require_once(VQMod::modCheck(DIR_SYSTEM . 'library/weight.php'));
	require_once(VQMod::modCheck(DIR_SYSTEM . 'library/length.php'));
	require_once(VQMod::modCheck(DIR_SYSTEM . 'library/cart.php'));
	require_once(VQMod::modCheck(DIR_SYSTEM . 'library/affiliate.php'));

*Note the affiliate library file may not exist on older systems*. Basically any `require_once(DIR_SYSTEM . 'library/xxxxxxxx.php');`
needs to be changed to use the `VQMod::modCheck` above in the same format. This also applies to any additional require_once files in the next step
  7. Edit your *admin/index.php* file

  8. FIND:

	// Startup
	require_once(DIR_SYSTEM . 'startup.php');
	
	// Application Classes
	require_once(DIR_SYSTEM . 'library/currency.php');
	require_once(DIR_SYSTEM . 'library/user.php'));
	require_once(DIR_SYSTEM . 'library/weight.php');
	require_once(DIR_SYSTEM . 'library/length.php');

  9. REPLACE WITH:

	// vQmod
	require_once('../vqmod/vqmod.php');
	VQMod::bootup();
	
	// VQMODDED Startup
	require_once(VQMod::modCheck(DIR_SYSTEM . 'startup.php'));
	
	// Application Classes
	require_once(VQMod::modCheck(DIR_SYSTEM . 'library/currency.php'));
	require_once(VQMod::modCheck(DIR_SYSTEM . 'library/user.php'));
	require_once(VQMod::modCheck(DIR_SYSTEM . 'library/weight.php'));
	require_once(VQMod::modCheck(DIR_SYSTEM . 'library/length.php'));

  10. Load your store homepage and verify it works.

  11. Using FTP, verify that there are new "vq" files in the "vqmod/vqcache" folder.

  12. If yes, then you are ready to start downloading or creating vQmod scripts.

Done!

###How to install manually (pre 2.4.0)
https://code.google.com/p/vqmod/source/browse/wiki/Install_OpenCart.wiki?r=104