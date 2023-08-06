## Step 1: Install Core
First download core from http://tinycorelinux.net/downloads.html and burn the iso to some form of installation media (or in my case, create a vm for it)  
Boot the system into the installation media. Core should boot and you will be greeted by `tc@box~#`.   
Since tiny core is so barebones, we need to download an installer to help with formating, bootloader, etc.  Run the following command to download the official installer `tce-load -wi tc-install.tcz`  
Once it has finished downloading, type `sudo tc-install.sh` to start the installer.  
After you have finished the installation, shut down, remove the install media, and boot into the system.  

## Step 2: Install Java
core comes with a primative package installer called appbrowser. In tiny core packages are called extensions, it can be a bit confusing.  
To install java type: `tce-ab`  
You will be greeted with some options, press `s` to search for a extension  
Search for java by typing "openjdk"  
You will be given a list of extensions, select the number corrosponding to the extension you want to install. In my case I chose 7 which corrosponded to `openjdk-8-jre.tcz`. (if there is only one package this stage is ignored)  
You should now see a page with the details of the extension, press `q` to exit out of this.  
Finally, press `I` begin the installation.  
Once the install is completed, press `q` to return to the command line.  

The java binaries are now installed to `/usr/local/openjdk*/jre/bin` (this might slightly vary depending on the extension you installed)  

## Step 3: Add the java binaries to path.

First we need a text editor, use the instructions from step 2 to install nano or vim or emacs or whatever  
Edit the .ashrc file in you're home directory and add `export PATH="/usr/local/openjdk-8/jre/bin:$PATH"` you may have to modify the bin directory for java slightly depending on you're install  
Type `exit`, and then relogin (username is `tc` by default)  
Type `java`, you should get the help info.  

Hopefully this helps!  


Refrence: https://wiki.tinycorelinux.net/
