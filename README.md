
IR Forensic ARTifact pull (irFArtpull)

DESCRIPTION:

irFARTpull is a PowerShell script utilized to pull several forensic artifacts from a live Windows 7, 8, Server 2008, and Server 2012 systems on your network. 
		
Artifacts it grabs:
- Disk Information
- System Information
- User Information
- Network Configuration
- Netstat info
- Route Table, ARP Table, DNS Cache, HOSTS file
- Running Processes
- Services
- Event Logs (System, Security, Application)
- Prefetch Files
- $MFT
- NTFS $LogFile
- Registry Files
- User NTUSER.dat files
- Java IDX files
- Internet History Files (IE, Firefox, Chrome)
	
When done collecting the artifacts, it will 7zip the data and yank the info off the box for off-line analysis. 
		
NOTEs: 
- All testing done on PowerShell v3 oe v4
- Requires RawCopy64.exe for the extraction of MFT$ and NTUSER.DAT files.
- Autorunsc - Command line version of Autoruns; shows the programs configure to run during login, system bootup, and application plug-ins.
- Requires 7za.exe (7zip cmd line) for compression w/ password protection
	
Assumed Directories:
- c:\windows\temp\IR - Where the work will be done (no need to create)
		
***As expected: Must be ran a user that will have Admin creds on the remote system. The assumption is that the target system is part of a domain.
	
LINKs:  
	
irFARTpull main - https://github.com/n3l5/irFARTpull
	
Links to required tools:
- RawCopy64.exe - Part of the mft2csv suite, RawCopy can be downloaded here: https://code.google.com/p/mft2csv/
- Autorunsc - Command line version of Autoruns; shows the programs configure to run during login, system bootup, and application plug-ins. https://technet.microsoft.com/en-us/sysinternals/bb963902.aspx
- 7za.exe - Part of the 7-Zip archiver, 7za can be downloaded from here: http://www.7-zip.org/
	
Various tools for analysis of the artifacts:
- RegRipper - Tool for extracting data from Registry and NTUSER.dat files. https://code.google.com/p/regripper/
- WinPrefetchView - utility to read Prefetch files. http://www.nirsoft.net/utils/win_prefetch_view.html
- MFTDump - tool to dump the contents of the $MFT. http://malware-hunters.net/2012/09/
- Triforce ANJP - tool to examining the MFT, LogFile, and USN. https://www.gettriforce.com/product/anjp-free/
