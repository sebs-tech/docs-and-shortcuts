# Change hostname to a WSL distribution

### 1. Enable necessary stuff in Windows 
```bash
Control Panel > Programs > Programs and Features > Turn Windows features on or off
```

Enable: 
- Virtual Machine Platform 
- Windows Hypervisor Platform 

Reboot

### 2.WSL
```bash
$ sudo nano /etc/wsl.conf

[boot]
systemd = true 

[network]
hostname = your_new_hostname
generateHosts = false 
```

### 3. Add entries to /etc/hosts
```bash
$ sudo nano /etc/hosts

# [network]
# generateHosts = false
127.0.0.1       localhost
127.0.1.1       your_new_hostname.localdomain     your_new_hostname
```


### 4. Reboot WSL

```bash
$ exit 
$ wsl --shutdown
```