
# <h1 align="center">Kali Nethunter Termux</h1>
 
<p align="center">Kali Linux NetHunter on Termux is a powerful tool for security professionals and enthusiasts. It allows users to perform a variety of security assessments on their Android devices without rooting them.</p>

<img src="https://github.com/xiv3r/Kali-Linux-Termux/blob/main/kali_nethunter/kalivnc.jpg">

<br>

# Requirements
- Arm64
- 15GB Storage spaces
- [Termux](https://github.com/termux/termux-app/releases/download/v0.118.2/termux-app_v0.118.2+github-debug_arm64-v8a.apk)
- [VNC](https://store.nethunter.com/repo/com.offsec.nethunter.kex_11525001.apk)

# Auto Install
- ### Kali Nethunter Full with VNC
```
pkg update && pkg install wget -y && wget -qO- https://raw.githubusercontent.com/xiv3r/Kali-Linux-Termux/refs/heads/main/kali_nethunter/kali-full | bash && kali
```
- ### Kali Nethunter Minimal without VNC
```
pkg update && pkg install wget -y && clear && wget -qO- https://raw.githubusercontent.com/xiv3r/Termux-Pentesting-Distro/refs/heads/main/KaliLinux/Chroot/kali-minimal | bash && kali
```
> - Setup for kali nethunter full
> - After the installation type the following commands in termux terminal

> - Setup VNC password
```diff
kali vnc passwd
```        
> - Run VNC service `127.0.0.1:5901`
```diff
kali vnc &
```
<details><summary></summary>
<img src="https://github.com/xiv3r/Kali-Linux-Termux/blob/main/kali_nethunter/vncsetup.png">
</details>

> Next Open the VNC client and add the address `127.0.0.1:5901` and type `kali` as username and your vnc `password`

## Login User
```
kali
```
## Login Root
```
kali -r
```
## Logout
```
exit
```
## Uninstall
```
kali-uninstall
```

<br><br>

# Terminal
> Password: `kali`

<img src="https://github.com/xiv3r/Kali-Linux-Termux/blob/main/kali_nethunter/kalinh.png">


<details><summary>

## Disable phantom process killer
 </summary>
 
> " Process completed (signal 9) - press Enter "

## Download & Install
- Download [Shizuku](https://github.com/RikkaApps/Shizuku/releases) and [Ashell](https://github.com/DP-Hridayan/aShellYou/releases) then enable developer options wireless debugging mode through shizuku and pair the key from the notification
- Permit ashell from shizuku settings 
- Paste the adb commands below on ashell

- Execute the commands below, These commands will disable the phantom process killer:
```
adb shell /system/bin/device_config set_sync_disabled_for_tests persistent
```
```
adb shell /system/bin/device_config put activity_manager max_phantom_processes 2147483647
```
```
adb shell settings put global settings_enable_monitor_phantom_procs false
```
- To verify:
```
adb shell /system/bin/dumpsys activity settings | grep max_phantom_processes
```
```
adb shell /system/bin/device_config get activity_manager max_phantom_processes
```
</details>

