# Archlinux 
## Arch linux install fresh & first steps
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
## Error and solution
jdk-openjdk and jre-openjdk are in conflict
```
sudo pacman -R jdk-openjdk jre-openjdk
sudo pacman -S jdk-openjdk
sudo pacman -Syu
```


