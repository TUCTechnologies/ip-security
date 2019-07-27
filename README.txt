How to add Block County IP's in Windows Firewall with PowerShell.

Step 1: Create a directory for working with PowerShell and PowerShell Scripts. Example - C:\ip-security

Step 2: Download the PowerShell script Import-Firewall-Blocklist.ps1 from http://www.gregsitservices.com/ip-security/ip-security-package.zip and extract the PowerShell script Import-Firewall-Blocklist.ps1 to your C:\ip-security folder. *If you're reading this file, you most likely already obtained this package in a modified form*

Step 3: Go to https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2 for a reference of which two letter code corresponds with the country that is wanting to be blocked from accessing your Windows instance. For each country, place the two letter code on a separate line inside of "countrycodes.txt" in the root of the project directory

Suggested country codes:
 1) CHINA (CN)
 2) KOREA, DEMOCRATIC PEOPLE'S REPUBLIC OF (KP)
 3) KOREA, REPUBLIC OF (KR)
 4) RUSSIAN FEDERATION (RU)

Step 4: Run PowerShell and Administrator (right click PowerShell and select Run As Administrator).

Step 5: Type without quotes "PowerShell.exe -ExecutionPolicy Bypass" - This will set the scripts Policy of PowerShell to run so that it can make the Windows Firewall rules.

Step 6: Begin importing the country zone ranges into your Windows Firewall:

  .\Import-Firewall-Blocklist.ps1

Zone files will be downloaded from http://www.ipdeny.com/ipblocks/data/countries and saved into the zones folder.

Step 7: Just for precaution let's now set PowerShell back to Restricted Access on Scripts. Type without quotes "PowerShell.exe -ExecutionPolicy Restricted".

That's it we are done... It is suggested to keep a copy of the country codes file and zones folder.

Below is how you can remove entries:

 .\Import-Firewall-Blocklist.ps1 -DeleteOnly

For the protection of the person running the script, it is required to press a key after the zones have been imported. This is important when running the script on remote systems. Failing to press a key assumes that connection to the remote system has been lost, thus changes are rolled back.


ENJOY!


Best regards,

Greg (TRI0N) Munson
Brandon Buchanan (willjasen)
