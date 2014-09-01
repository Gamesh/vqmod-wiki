#How to Upgrade vQmod

  1. Download the latest version (use the opencart specific version if using opencart)
  2. Unzip the contents of the download. This should give you a folder called "vqmod" with an "install' and "xml" folder inside, amongst others.
  3. Upload that folder to your site's current "vqmod" folder via FTP. Overwrite all files when prompted. Do NOT drop the new folder on top of the current vqmod folder as that will generally upload the entire vqmod directory into a subfolder inside the main directory, instead of overlaying the existing install. All files in the 2 folders will merge, and the new files will overwrite the old files. But all your existing xml files will be safe.
  4. If you are coming from an older version of vQmod (pre-2.4.0) then you will need to re-run the installer to update the syntax of the vQmod include code. If you are not sure, then feel free to run the installer anyway. It will not hurt anything. It will just tell you vQmod is already installed.

That's it!

If you are struggling to upgrade using the simple installer upgrade in OpenCart, simply upload fresh index.php files to both the main directory, and the admin directory and then run the installer