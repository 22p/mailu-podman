loginctl enable-linger $UID

sudo sysctl net.ipv4.ip_unprivileged_port_start=0

cd ~/.config/systemd/user/



podman network create --subnet 192.168.203.0/24 mailu_default

systemctl --user start container-mailu_*

systemctl --user enable container-mailu_*

podman exec mailu_admin_1 flask mailu admin admin domain.com PASSWORD

podman  images --format "{{.Repository}}:{{.Tag}}"  | xargs -L1 podman pull
