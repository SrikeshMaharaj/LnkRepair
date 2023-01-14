# LnkRepair
SI MO497128

Creates a new PowerShell drive (HKU) that is rooted in the HKEY_USERS registry key. It then defines the location of the All User Profile's start menu programs folder and assigns it to the $allprogsm variable. Next, it defines a consolidated source path for shortcuts and uses the Get-ChildItem cmdlet to retrieve all the shortcut files in that location and assigns them to the $shortcuts variable.

The script then loops through each shortcut and uses the WScript.Shell com object to create a new object that defines the shortcut path and target path. The script checks if the target path exists and if it does, it replaces the source path with the target path and copies the shortcut to the new location. After that, the script is fixing User Taskbar by getting the selected user SID from the registry, converting the byte array from the registry to a string, replacing some characters and splitting the string into an array. Then it loops through each line of the taskbar, checking if it's a shortcut and if the file path exists, if it doesn't it will define the missing file name and the path of the shortcut and get the missing file and copy it to the desired location.
