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
    *gpedit.exe ->User Configuration ->Administrative Templates ->Windows Components ->Windows Copilot ->set Turn off Windows Copilot to Enabled *
</p>
