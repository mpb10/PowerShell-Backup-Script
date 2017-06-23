# PowerShell-Backup-Script
https://github.com/ForestFrog/PowerShell-Backup-Script

A PowerShell script used to backup files.


**Scripts written by ForestFrog**

**June 23th, 2017**

**v1.1.0**
#

 - [INSTALLATION](#installation)
 - [USAGE](#usage)
 - [CHANGE LOG](#change-log)
 - [ADDITIONAL NOTES](#additional-notes)
 
#

# INSTALLATION

These scripts require Windows PowerShell and 7-Zip to function. PowerShell comes pre-installed in Windows 10 but otherwise can be downloaded here: https://www.microsoft.com/en-us/download/details.aspx?id=50395. 7-Zip can be downloaded here: http://www.7-zip.org/download.html

**Download PowerShell-Backup-Script script here:** https://github.com/ForestFrog/PowerShell-Backup-Script/archive/master.zip

Download the project .zip file, extract it to a folder, and run the `Backup_Installer.ps1` shortcut. The script will be installed to the folder `C:\Users\%USERNAME%\Backup Script`. A desktop shortcut and a Start Menu shortcut will be created. Run either of these to use the script. 

To update the script, delete the following folder, download the new version and install it:

	C:\Users\%USERNAME%\Backup Script\scripts
Make sure you don't delete any of the .txt files!

#

To uninstall these scripts, delete the Backup Script folders located at `C:\Users\%USERNAME%\Backup Script` and `%APPDATA%\Microsoft\Windows\Start Menu\Programs\Backup Script`, as well as the desktop shortcut.


# USAGE

Run either the desktop shortcut or the Start Menu shortcut. Choose option `1` to choose the folder to be backed up and the folder to which the backup is to be saved. By default the script will backup the user's `Documents` folder to `E:\Backups`. Make sure you choose the proper drive when backing up a folder. Alternatively, users can choose option `2` at the main menu to backup folders listed in the `backuplist.txt` file which is found at `C:\Users\%USERNAME%\Backup Script`.

**New in version 1.1.0**, users can save a list of folders to be backed up in the text file "C:\Users\%USERNAME%\Backup Script\backuplist.txt". One line at a time, list the path of each folder that is to be backed up, with the first line being the path of where to save the backups. Once the `backuplist.txt` file is set, choose option 2 on the main menu. Confirm that the information is correct and then begin the process.

#

**New in version 1.1.0**, users can list playlists in the `audioplaylist.txt` and `videoplaylist.txt` files located in `C:\Users\%USERNAME%\Youtube-dl`. List any playlist URL's one line at a time that you would like to download video from in the `videoplaylist.txt` file. The same goes for the `audioplaylist.txt` file. To download from these files, choose option `3` in the main menu or use the -FromFiles parameter switch if calling the script from the command line. Currently, playlists downloaded form the video playlist will be automatically converted to .webm

**New in version 1.2.0**, users can convert downloaded videos to other formats using  ffmpeg options which can be modified in option `4` of the main menu, "Settings". Only videos being downloaded will be converted, not audio downloads. This feature has not yet been implemented into the parameters that can be passed to the script.

#

For advanced users, the backup.ps1 script, which is found in the folder `C:\Users\%USERNAME%\Backup Script\scripts`, can be passed parameters so that this script can be used in conjunction with other scripts or forms of automation. Make sure you have 7z.exe added to your PATH.

**backup.ps1's parameters are as followed:**

	-InputPath <path>
		Folder to be backed up.
    
	-OutputPath <path>
		Location where to save the backup.


# CHANGE LOG

	1.1.1 	June 23rd, 2017
    		Uploaded to Github.
    		Condensed installer to one PowerShell script
		Edited documentation
    
	1.1.0	June 12th, 2017
		Added backing up folders listed in backuplist.txt


# ADDITIONAL NOTES

This script uses the 7-Zip program to compress folders for backing up. 7-Zip is licensed under the GNU LGPL license and its source code can be found at http://www.7-zip.org/.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.