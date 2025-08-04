networking error solve problem
--------------------------------------------------
sudo dhcpcd


internet not connection issue
--------------------------------------------------
su
bash -c 'echo -e "[Resolve]\nDNS=8.8.8.8\nFallbackDNS=1.1.1.1" > /etc/systemd/resolved.conf'
sudo ln -sf /run/systemd/resolve/resolv.conf /etc/resolv.conf
systemctl enable --now systemd-networkd
systemctl enable --now systemd-resolve




post installation
------------------------
su root
visudo
uncomment  - %wheel area
usermod -aG wheel foysal
su foysal
sudo pacman -Syu



