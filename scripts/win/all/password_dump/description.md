##Windows Password Dump
Author: Hak5Darren with the help of:
`@gentilkiwi, @Mubix, redmeatuk, shutin, DyFukA, Microsoft, Sysinternals, 7zip`

Description: "Backup" Windows Passwords without setting off AntiVirus
Dumps memory of lsass.exe using Microsoft Sysinternals util ProcDump
Passwords can be later be extracted using mimikatz.

Firmware: Use [c_duck_v2.1.hex](https://cdn.rawgit.com/midnitesnake/USB-Rubber-Ducky/master/Firmware/Images/c_duck_v2.1.hex) firmware (Twin Duck) to execute from SD
card labeled "DUCKY" and save log file as %COMPUTERNAME%_lsass.dmp
Include procdump.exe in the lib\ subfolder of DUCKY SD card. Download ProcDump from:
http://technet.microsoft.com/en-us/sysinternals/dd996900.aspx

Include 7za.exe in the lib\ subfolder of DUCKY SD card. Download 7zip command line version from:
http://www.7-zip.org/download.html

_**N.B. 7za.exe is included in this repository, however, due to licensing restrictions, procdump.exe is not.**_

Target: Windows Vista/7/8, Win32/x64


##Post Exploitation
From your PC copy the %COMPUTERNAME%_lsass.dmp off the results\ folder on the DUCKY SD card to a 
directory including the version of mimikatz for your targets architecture
(NT5 win32, NT5 x64, NT6 win32 or NT6 x64) and run the following commands
mimikatz.exe <enter>
sekurlsa::minidump %COMPUTERNAME%_lsass.dmp <enter>
sekurlsa::logonPasswords full <enter>
