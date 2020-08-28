# Powershell---tutorial

This is a tutorial as some of the important powershell commands

## Commonly used PSADT env variables
$envCommonDesktop           # C:\Users\Public\Desktop
$envCommonPrograms          # C:\ProgramData\Microsoft\Windows\Start Menu\Programs
$envProgramFiles            # C:\Program Files
$envProgramFilesX86         # C:\Program Files (x86)
$envProgramData             # c:\ProgramData
$envUserDesktop             # c:\Users\{user currently logged in}\Desktop
$envUserStartMenuPrograms   # c:\Users\{user currently logged in}\AppData\Roaming\Microsoft\Windows\Start Menu\Programs
$envSystemDrive             # c:
$envWinDir                  # c:\windows

# cmd to execute the exe file 
Execute-Process -Path "$dirFiles\installer_file.exe" -Parameters '/silent' -WindowStyle 'Hidden'

# For silent execution you can try in -Parameters
/silent 
/quite
/qn
'--mode unattended'

# cmd to install the exe file 
Execute-Process -Path "$dirFiles\DirectX\DXSetup.exe" -Parameters '/silent' -WindowStyle 'Hidden'

# cmd to uninstall the exe file 
Execute-Process -Path "C:\Program Files (x86)\unintall_path\Uninstall-xc8-v2.20.exe" -Parameters '--mode unattended'

# Copy file/folder/subfolder
Copy-File -Path "$dirFiles\Source_folder_name" -Destination "C:\Program Files (x86)\Destination_folder_name\" -Recurse

# remove shortcuts
Remove-File -Path "C:\Users\Public\Desktop\File_name.lnk"

# Remove Folder
Remove-Folder -Path "Folder_Path"

# Install certificate (save the certificate, after installing the exe)
		Execute-Process -Path "certutil.exe" -Parameters "-f -addstore -enterprise TrustedPublisher `"$dirFiles\Certs\Microchip Techology_1.cer`""
		Execute-Process -Path "certutil.exe" -Parameters "-f -addstore -enterprise TrustedPublisher `"$dirFiles\Certs\Microchip Techology_2.cer`""
		Execute-Process -Path "certutil.exe" -Parameters "-f -addstore -enterprise TrustedPublisher `"$dirFiles\Certs\Microchip Techology_3.cer`""
		
		Write-Log -Message "Imported Cert" -Source $deployAppScriptFriendlyName
    
    
