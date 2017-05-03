# A local, virtualized Windows environment

Reference impl:  https://github.com/luciusbono/Packer-Windows10

Find Windows trial product keys here:
https://technet.microsoft.com/en-us/library/jj612867.aspx?f=255&MSPPError=-2147217396


## Current State
I'm not positive that all of the packer scripts will run w/o intervention.  I need to take the time to do an entire automated build.
I think there may be an issue running the `configure-winrm` script after successful completion of the `update-windows` script, which is driven from `autounattend.xml`.
TODO: Fix this.


## Setup

### Prereqs
```
brew cask install packer
brew install vagrant
```

You need to find a Win10_Pro `.iso` file.  It goes in `iso/Win10_1607_English_x64.iso`.
If you change the path or filename, the change must be reflected in `packer/win_10.json`.
`TODO:` Automate correct .iso download, I think Packer supports this.

### Running
Note, this takes multiple hours.
```
cd packer
packer build win_10.json
vagrant up
```

### Re-Running
```
rm -rf packer/output-virtualbox-iso
vagrant reload
```

## Using

RDP is enabled, it's a better experience to use Microsoft Remote Desktop.  IP is set to `10.10.10.10` in `Vagrantfile`.
If you'd rather use the VirtualBox UI, change the `vb.gui` value in `Vagrantfile`.

Vagrant's default synced folder is set up.  In the guest, `C:\vagrant` is synced to this directory.