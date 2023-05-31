# MMANUAL DE INSTALAÇÕES DOCKER
-------------------------------

## Atualizar e reiniciar a vps com ubuntu 22.04
apt update -y && apt upgrade -y && init 6


## Instalar o docker
curl -fsSL https://get.docker.com | sh


## Instalar o portainer 
docker volume create portainer_data
docker run -d -p 8000:8000 -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest


## Instalar o n8n
docker run -d --restart always --name n8n -p 5678:5678 -v ~/.n8n:/home/node/.n8n -e WEBHOOK_TUNNEL_URL=https://sua-url.com.br docker.n8n.io/n8nio/n8n
