
### Check the list of available WSL distros 
[Available Distributions Link](https://learn.microsoft.com/en-us/windows/wsl/install-manual#downloading-distributions)

### PowerShell
```bash
# Substitute the drive on which you 
# want WSL to be installed if not D:
Set-Location D:

# Create a directory for our installation and change to it, we'll call it WSL:
New-Item WSL -Type Directory
Set-Location .\WSL

# Using the URL you found above, download the appx package:
curl.exe -L -o Linux.appx <distribution_package_url>

# Make a backup and unpack:
Copy-Item .\Linux.appx .\Linux.zip
Expand-Archive .\Linux.zip

Set-Location Linux
# look for correct appx file:
Get-Childitem -Filter *.appx
# rename to .zip so that Expand-Archive will work
ren .\Ubuntu_2204.1.7.0_x64.appx .\Ubuntu_2204.zip
Expand-Archive .\Ubuntu_2204.zip
Set-Location .\Ubuntu_2204
# Now exe should exist:
Get-Childitem -Filter *.exe
# run it
.\ubuntu.exe
```

### Option 2 

1. Export Ubuntu 

    - 
        ```bash
        # Create a backup folder on drive D:
        mkdir D:\backup
        ```
    -   ```bash
        # Export the Ubuntu distribution to a tar file in the backup folder
        wsl --export Ubuntu D:\backup\ubuntu.tar
        ```

2. Unregister existing distributions 

    - 
        ``` bash
        # Remove the existing Ubuntu distribution from drive C:
        wsl --unregister Ubuntu
        ```

3. Import Ubuntu to Drive Directory

    -
        ```bash
        # Create a new folder on drive D for the WSL installation
        mkdir D:\wsl
        ```
    -
        ```bash
        # Import the Ubuntu distribution from the backup tar file to the new folder on drive D
        wsl --import Ubuntu D:\wsl\ D:\backup\ubuntu.tar
        ```

4. Set Default User

    ```bash
    # Open the Ubuntu App Folder. You can do this by running the following command
    cd %userprofile%\AppData\Local\Microsoft\WindowsApps

    # Set the default user by running the following command and replacing <username> with your desired username
    ubuntu config --default-user <username>
    ```