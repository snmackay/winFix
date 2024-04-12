# winFix
<p> A repository of group policy editor flags and regedit commands that need to be set to make windows a useful operating system. <br>
    WARNING: no warranty is implied with any of this. You break your OS its your problem not mine. <br>    
</p>

# Group Policy Editor Flags
<p> The following are flags that need to be set via group policy editor. Note that this only works on windows
    11 Pro and not Home as gpedit.exe is not accessible on the home version of Windows 11. If you are on windows
    10 this is not a problem and will work on all versions of the operating system. Note that some of the flags
    listed are not going to be needed on windows 10 and are only needed on windows 11. These will be annotated. 
</p>

## Disable Windows CoPilot Integration
<p> Windows 11 (and potentially Windows 10) <br>
    Windows now has copilot integration. If you dont want this, set the following path: <br>
    
    gpedit.exe ->User Configuration ->Administrative Templates ->Windows Components ->Windows Copilot ->Turn off Windows Copilot ->Enabled
</p>

## Disable Automatic Updates
<p> Windows 10 & Windows 11 <br>
    
    gpedit.exe ->Computer Configuration ->Administrative Templates ->Windows Components ->Windows Update ->Manage end user experience ->Configure Automatic Updates ->Disabled
</p>

## Disable Driver Updates in Windows Update
<p> Windows 10 & Windows 11 (windows 11 has a setting in settings for this on Windows 11 pro) <br>
    Note: On Windows 11 on some OEM systems not setting this will allow your bios to get automatically updated. This is NOT A GOOD IDEA. <br>
    Win10: <br>
    
    gpedit.exe ->Computer Configuration > Administrative Templates > Windows Components > Windows Update ->Do not Include drivers with Windows Update ->Enabled 
Win11: 

    gpedit.exe ->Computer Configuration > Administrative Templates > Windows Components > Windows Update ->Manages updates offered from Windows Update -> Do not include drivers with Windows Update ->Enabled 
</p>

## Remove Web Results From Search
<p> Windows 11 and Windows 10 <br>
    Microsoft loves to add web content to search as well as index a lot of stuff. The directory in gpe linked here has a bunch of stuff worth flagging <br>
    
    gpedit.exe ->Computer Configuration > Administrative Templates > Windows Components > Search ->Don't search the web or display web results in Search ->Enabled 
    gpedit.exe ->Computer Configuration > Administrative Templates > Windows Components > Search ->Don't search the web or display web results in Search over metered connections ->Enabled 
Optional: <br>
 
    gpedit.exe ->Computer Configuration > Administrative Templates > Windows Components > Search ->Prevent indexing email attachments ->Enabled 
    gpedit.exe ->Computer Configuration > Administrative Templates > Windows Components > Search ->Prevent indexing Microsoft Office Outlook ->Enabled   
</p>

## Permanently Remove OneDrive
<p> Windows 11 and Windows 10<br>
    This one is not essential but its probably for the best to do it. Onedrive can reinstall itself and if you use an online account it can mess up<br>
    
    gpedit.exe ->Computer Configuration > Administrative Templates > Windows Components > OneDrive -> Prevent the usage of OneDrive for file storage -> Enabled 

</p>

# Registry Tweaks

## Restore Old Right Click Context Menu on Windows 11
<p> This is useful if you want the old context menu <br>

**ADDING** : <br>
1: Run Windows Terminal as admin<br> 
2: Run the following command: <br>
    
    reg.exe add "HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}\InprocServer32" /f /ve             
3: Restart <br>
<br>    
**RESTORE** (Useful to do before updating Windows 11): <br>
1: Run Windows Terminal as admin <br>
2: Run the following command: <br>
        
    reg.exe delete "HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}" /f 
3: Restart <br>
</p>
