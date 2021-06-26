# AutoSetup

My personal automated setup scripts to fit a variety of my needs and is customizable depending on the device.

This kind of thing is perfect for [Ansible](https://www.ansible.com/) but I wanted to make this for myself as a project before going into learning Ansible.

## About this

This project is still incomplete and does not have necessary components uploaded to GitHub yet.
It is not recommended you try to run any of this but feel free to look around.

## Instructions

1. Download and run the initialization script
    1. Initialization will install the package manager Chocolatey or Homebrew depending on your platform.
    2. Initialization will then use the package manager to install Python3.
2. The final step of initialization will grab needed files and start the Python script to install packages noted in the [InstallList](./InstallList.csv) file.
    1. This execution of the script will be moved to a separate step so you can create a list before executing.

### Windows
---

- A user profile likely needs to be created.
    - Testing is still needed to see if this works on setup prior to creating a profile.
- Administrator rights are required for proper operation.
- Recommended Windows 10 version 1803/preview 17063 or later.
  - [17063](https://techcommunity.microsoft.com/t5/containers/tar-and-curl-come-to-windows/ba-p/382409) preview and [1803](https://devblogs.microsoft.com/commandline/windows10v1803/) release or later as curl is built in.
- Without at least these versions manual installation of [cURL](https://curl.se/) would be needed.


Running the initialization script:
In an Administrator Command Prompt window run:
```
curl -fsSL -o ./ASTemp/initWin.bat https://raw.githubusercontent.com/kyle-lilley/AutoSetup/main/initWin.bat
start .\ASTemp\initWin.bat
```

### MacOS
---

- An Administrator profile has to be setup and used.
- Recommended MacOS Mojave or later for compatibility.
  - Currently untested on ARM based Apple Silicon macs.
- Remaining requirements should be setup automatically by the script.
  - XCode tools should install via the script, if not it will have to be installed manually to be able to install Homebrew.

Running the initialization script:
In a terminal window run:
```
curl -fsSL -o ./ASTemp/initMac.sh https://raw.githubusercontent.com/kyle-lilley/AutoSetup/main/initMac.sh
.\ASTemp\initMac.sh
```

If there are problems opening the file, you may have to use [chmod](https://support.apple.com/guide/terminal/make-a-file-executable-apdd100908f-06b3-4e63-8a87-32e71241bab4/mac) to make it executable.
```
chmod 755 .\ASTemp\initMac.sh
```

### Linux
---

- An Administrator profile has to be setup and used.
- Currently untested entirely, my first tests will be on Raspberry Pi OS and Ubuntu.
- Linux is currently set to use Homebrew as well but compatibility will be added to use apt-get instead of or along side Homebrew for platforms like Raspberry Pi OS and Ubuntu that come with it preinstalled.

Running the initialization script:
In a terminal window run:
```
curl -fsSL -o ./ASTemp/initLinux.sh https://raw.githubusercontent.com/kyle-lilley/AutoSetup/main/initLinux.sh
.\ASTemp\initLinux.sh
```
