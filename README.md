# winFix
A repository of group policy editor flags that need to be set to make windows a useful operating system.

# Flags
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
    Win10: gpedit.exe ->Computer Configuration > Administrative Templates > Windows Components > Windows Update ->Do not Include drivers with Windows Update ->Enabled <br>
    Win11: gpedit.exe ->Computer Configuration > Administrative Templates > Windows Components > Windows Update ->Manages updates offered from Windows Update -> Do not include drivers with Windows Update ->Enabled <br>
</p>

## Remove Web Results From Search
<p> Windows 11 and Windows 10 <br>
    Microsoft loves to add web content to search as well as index a lot of stuff. The directory in gpe linked here has a bunch of stuff worth flagging <br>
    gpedit.exe ->Computer Configuration > Administrative Templates > Windows Components > Search ->Don't search the web or display web results in Search ->Enabled <br>
    gpedit.exe ->Computer Configuration > Administrative Templates > Windows Components > Search ->Don't search the web or display web results in Search over metered connections ->Enabled <br>
    Optional: <br>
    gpedit.exe ->Computer Configuration > Administrative Templates > Windows Components > Search ->Prevent indexing email attachments ->Enabled <br>
    gpedit.exe ->Computer Configuration > Administrative Templates > Windows Components > Search ->Prevent indexing Microsoft Office Outlook ->Enabled <br>    
</p>

## Permanently Remove OneDrive
<p> Windows 11 and Windows 10<br>
    This one is not essential but its probably for the best to do it. Onedrive can reinstall itself and if you use an online account it can mess up<br>
    gpedit.exe ->Computer Configuration > Administrative Templates > Windows Components > OneDrive -> Prevent the usage of OneDrive for file storage -> Enabled <br>

</p>
