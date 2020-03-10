# RPICoin Bootstrap resources & information


# Automated the process to always have a recent bootstrap.bin available for download
		Bootstrap will run via a cronjob on a weekly basis

> Please see bootstrap_generator.sh


## Instructions for the RPICoin USERS - but please use this method only if you are stuck while trying to sync your wallet. 

* Please always backup your wallet.dat and private key before making any changes.
* Turn off the wallet and download our bootstrap file https://rpicoin.com/bootstrap.dat 
* Move the bootstrap.dat you just downloaded to the %appdata%/Roaming/RPICOIN folder.

**Recommended to have a higher success ratio! (just do it):**
 Delete all the files **EXCEPT your wallet.dat** in the RPICOIN data directory, make sure you now only have the **wallet.dat** and the just moved **bootstrap.dat** files in there - or a clean update/installation. Or just create a new folder and copy all the RPICOIN folder content to it, in case you need the files again.


#### Locations of the RPICOIN data directory for each operating system:

**Linux =**
		~/.rpicoin/
**or**
		/root/.rpicoin/ **or** /home/<yourlinuxusername>/.rpicoin

**MacOS =** 
		$HOME/Library/Application Support/rpicoin/
**or**
		/Users/username/Library/Application Support/rpicoin/

**Windows:**
		%APPDATA%/Rpicoin
**or**
		C:\Users\<yourusername>\AppData\Roaming\Rpicoin

* **Start your wallet again**
It should start indexing/updating the blocks shortly after, after it finishes the syncing process, the bootstrap.dat file will be automatically renamed to bootstrap.dat.old. You can safely delete the file if you wish.

Note: If your wallet stays hidden during the process, or appears to have frozen, just give it enough time (or check if the blk000*.dat files in the data directory are increasing in size).