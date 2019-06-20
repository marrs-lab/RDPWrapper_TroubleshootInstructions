## RDP Wrapper Set up on Windows 10

*note: these instructions only apply to RDP wrapper v1.6.2*
Date: 06/20/2019
Authors: Teddy Marchildon and Alexandra DiGiacomo

1. Sign in as the local admin 
2. Go to the [RDP Wrapper git repo](https://github.com/stascorp/rdpwrap/releases) and install the .zip file
3.  Open the RDPWrap-v1.6.2 .zip file 
4. Run the install file
5. Run the RDPConf file and keep the generated window up
6. Check the listener state in the diagnostics box. If the listener state reads "Listening. [fully supported]," then you're good to go. If the current version is not supported (denoted in red) continue to the following steps.
7. Open the Command Prompt as an administrator by right clicking on the Command Prompt application icon. Type "net stop term service" and press enter. 
8. Make note of Service State version (ex: ver. 10.0.14393.2906), denoted in the top right hand corner of the dialogue box. 
9. Find the rdpwrap.ini file (config file). Likely located in C:/Program Files/RDP Wrapper/rdpwrap.ini
10.  Search (ctrl F)  your service state version in the rdpwrap.ini file in this repository. It should be located in this file twice, once by itself and once with -SL attached to the end. 
11. If your version number is included in the file, replace your current local rdpwrap.ini file with the downloaded rdpwrap.ini file from this repository.
	11. If access is denied, try opening the notepad app, right clicking the notepad application icon, clicking "run as administrator" and copy-pasting the .ini file text from this repository into the new notepad file. **Save as rdpwrap.ini in the original location, overwriting the existing file**
12. If your version number is not included in the file, check [this repository]([https://github.com/fre4kyC0de/rdpwrap](https://github.com/fre4kyC0de/rdpwrap)) for it. Follow steps 10 & 11 using the text from the .ini file associated with your service state. 
13. Type "net start term service" in the Command Prompt and press enter. 
14. Restart the computer 
