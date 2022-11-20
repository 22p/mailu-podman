sudo sysctl net.ipv4.ip_unprivileged_port_start=0
cd ~/.config/systemd/user/



systemctl --user start container-mailu_*
systemctl --user enable container-mailu_*
podman exec mailu_admin_1 flask mailu admin admin domain.com PASSWORD
