# Servarr setup

Ensure that docker is enabled and create volume for portainer:

```bash
sudo systemctl enable --now docker
docker volume create portainer_data
```

REF: [Install CE Server Docker linux](https://docs.portainer.io/start/install-ce/server/docker/linux)

Run Portainer outside of compose file:

```bash
docker run -d -p 8000:8000 -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:lts
```

Run compose up:

```bash
docker compose up -d
```
