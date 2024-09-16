# Antivirus-1

Microsoft Defender Antivirus to detect and remove malware from a Windows system.

From the taskbar, launch the File Explorer and navigate to C:\Evil.
In the Evil directory, right-click Sample1.zip and select 7-Zip > Extract Here.

When prompted, use the password infected to unzip the malware.
On the taskbar, click the Search icon and type virus, then select Virus & threat protection from the search results to open the Windows Security application.

Take note of the Current threats section on the Virus & Threat Protection page. Here you will see the last scan, the type of scan, if any threats were found, how long the previous scan took, and how many files were last scanned.

 <img src="https://i.imgur.com/BmibK5n.png" alt="Lab Screenshot" style="max-width: 100%; height: auto;">

 Under Virus & threat protection settings, click Manage settings, then confirm that Real-time protection is on.

The Real-time Protection function is responsible for actively scanning the file system for malware and removing any suspicious files that it detects. In the next steps, you will copy the malicious executable file from Sample1 to the C:\ drive and watch as Microsoft Defender Antivirus flags and removes the file.

 <img src="https://i.imgur.com/HWdjnOl.png" alt="Lab Screenshot" style="max-width: 100%; height: auto;">

 In the File Explorer, copy the malicious .exe file from the Sample1 folder, and paste it to the C:\ drive.

When prompted, click Continue to continue.

After pasting the file in the C:\ drive, you should see an alert in the lower-right corner indicating that a virus was detected. The file will disappear from the C:\ drive in a few seconds.

Note: The same malicious file was not detected in the C:\Evil folder because the Evil folder is excluded from Real-Time Protection.
In the Windows Security window, in the sidebar, click Virus & threat protection to return to the Virus & Threat Protection page.
Under Current threats, click Threat history to view previously detected threats.

Take note of the Quarantined Threats section, which includes a record of the malware that Windows Defender Antivirus just removed from the C:\ drive.
Under Quarantined Threats, click the arrow to expand the malware record, then click See details to see more information about the malware.

When prompted, click Yes to continue.
In the malware details window, click Learn more to open the Microsoft Security Intelligence page in Firefox.

Note: Firefox may take up to 60 seconds to open the first time.

Microsoft does not have much information about this malware sample. In the next step, you will run a search in Google to attempt to gather more information.
Copy the malware name, then paste the name into Google and run a search.

Review the Google results to learn more about this particle piece of malware.

It is also possible to run Windows Defender Antivirus scans using PowerShell. In the next steps, you will un-zip the malware sample in Sample2.zip, then remove the exclusion on C:\Evil and run a Windows Defender scan from PowerShell.
In the File Explorer, return to the Evil directory, then right-click Sample2.zip and select 7-Zip > Extract Here.

When prompted, use the password infected to unzip the malware.
In the Windows Security window, return to the Virus & Threat protection page and click Manage settings.
On the Settings page, click the toggle under Real-Time Protection to temporarily deactivate the Real-Time Protection feature.

This will prevent Windows Defender Antivirus from immediately flagging the Sample2 malware when we remove the exclusion on the Evil directory.
On the Settings page, scroll down to Exclusions and click Add or remove exclusions.

When prompted, click Yes to continue.
On the Exclusions page, click the down arrow to the right of the C:\Evil exclusion, then click Remove.

<img src="https://i.imgur.com/bvOTFgt.png" alt="Lab Screenshot" style="max-width: 100%; height: auto;">

Right-click the Windows Start icon, and select Windows PowerShell (Admin) to open a new PowerShell window.

When prompted, click Yes to continue.
At the PowerShell prompt, type Start-MPScan -ScanPath C:\Evil\ -ScanType CustomScan and press Enter to start a Windows Defender scan.

 <img src="https://i.imgur.com/NcMm5mK.png" alt="Lab Screenshot" style="max-width: 100%; height: auto;">

 Check the contents of the Sample1 and Sample2 folders.

Notice that the extracted malware has been removed.
In the Windows Security window, return to the Threat History page and review the malware record for Sample2 under Quarantined Threats.

Take note of the malware name, then run a Google search to learn more about its purpose.
