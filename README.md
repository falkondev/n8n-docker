# Configuração N8N usando Docker

## Requisitos
- Docker Engine ou Docker Desktop Instalado (https://docs.docker.com/engine/)

## Como usar
Crie um arquivo .env no diretório raíz do projeto e preencha as informações como no exemplo abaixo:

```
N8N_HOST="localhost"
N8N_PORT="5678"
N8N_PROTOCOL="http"

WEBHOOK_URL="http://localhost:5678/"
N8N_SECURE_COOKIE="false"
GENERIC_TIMEZONE="America/Sao_Paulo"

N8N_VOLUME_FOLDER="~/docker_volumes/n8n"
```
Em seguida, execute `docker compose up -d` para baixar a imagem e criar o container. Uma vez criado, acessar o host (no exemplo `http://localhost:5678` para acessar).

Para consultar os logs do n8n, execute `docker logs -f n8n`.

## Atualizando a versão do N8N
Caso o N8N tenha novas atualizações e você queira atualizar seu container, execute os seguintes passos:
```
docker compose pull
docker compose up -d
```
Os comandos acima irão forçar o docker a procurar novas atualizações para a imagem do N8N e em seguida irá montar o container novamente.