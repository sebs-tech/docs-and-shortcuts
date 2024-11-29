
## List installed distributions 
```bash
$ wsl --list --verbose
```

## List online distributions 
```bash
$ wsl --list --online
```

## Install a distribution
```bash
$ wsl --install -d <DistroName>
```

## **Install distribution to a Custom Location**
1. Export the distribution:
   ```bash
   wsl --export <DistributionName> <PathToExportedFile.tar>
   ```
   Example:
   ```bash
   wsl --export Ubuntu-22.04 D:\WSL\Ubuntu-22.04.tar
   ```

2. Import the distribution to a new location:
   ```bash
   wsl --import <NewDistributionName> <TargetFolder> <PathToExportedFile.tar>
   ```
   Example:
   ```bash
   wsl --import Ubuntu-22.04-Custom D:\WSL\Ubuntu-22.04 D:\WSL\Ubuntu-22.04.tar
   ```

3. Verify the new distribution:
   ```bash
   wsl --list --verbose
   ```

4. (Optional) Set the new distribution as the default:
   ```bash
   wsl --set-default <NewDistributionName>
   ```

5. (Optional) Delete the `.tar` file after import:
   ```bash
   del D:\WSL\Ubuntu-22.04.tar
   ```



## Shutdown a distribution 
```bash
$ wsl --terminate <DistributionName>
```

## Unregister a distribution 
```bash
$ wsl --unregister <DistributionName>
```
## Start a specific WSL 
```bash
$ wsl -d <DistributionName>
```
## Start a distro with a user 
```bash
$ wsl -d <DistroName> -u username
```








