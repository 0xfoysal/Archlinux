# Archlinux 
## Arch linux install fresh & first steps


## Arch linux install another step
primary install
```
ps aux | grep pacman
sudo rm /var/lib/pacman/db.lck
sudo pacman -Sy archlinux-keyring blackarch-keyring
sudo pacman-key --init
sudo pacman-key --populate
```
then another step Steps to Enable BlackArch and Install the Installer
Add the BlackArch Repository
```
curl -O https://blackarch.org/strap.sh
sudo chmod +x strap.sh
sudo ./strap.sh
```
Update Your Package Database:
```
sudo pacman -Sy
```
Install blackarch-installer
```
sudo pacman -S blackarch-installer
```
Run the installer
```
sudo blackarch-install
```
Available install mode choose ->  2nd option,  <br />
output mode -> 2nd option, <br />
verber mode -> 1st option, <br />
local optoin -> 1st option, <br />
keymap -> 1 <br />
host -> root <br />
network -> select dhcp <br />



## Error and solution
jdk-openjdk and jre-openjdk are in conflict
```
sudo pacman -R jdk-openjdk jre-openjdk
sudo pacman -S jdk-openjdk
sudo pacman -Syu
```



##outofbound
Clear the package cache and existing keys:
```
sudo pacman -Scc
sudo rm -r /etc/pacman.d/gnupg
```
Re-initialize the keyring and re-import keys:
```
sudo pacman-key --init
sudo pacman-key --populate archlinux
sudo pacman-key --populate blackarch
```
Manually retrieve and locally sign the BlackArch key:
```
sudo pacman-key --recv-keys F9A6E68A711354D84A9B91637533BAFE69A25079
sudo pacman-key --lsign-key F9A6E68A711354D84A9B91637533BAFE69A25079
```
Update the package databases:
```
sudo pacman -Sy
```

## jq intall
```
git clone https://github.com/jqlang/jq.git
cd jq
sudo pacman -S autoconf automake libtool make gcc
autoreconf -i
./configure --disable-maintainer-mode
make
sudo make install
jq --version
```
##updated go install
```
sudo pacman -S go
```
subjack
```
git clone https://github.com/haccer/subjack.git
cd subjack
go build
sudo mv subjack /usr/local/bin/
subjack -h
```
if get any errror like build
```
go mod init subjack
go get
go build
sudo mv subjack /usr/local/bin/
```
