# Configuração N8N usando Docker

## Requisitos

- Docker Engine ou Docker Desktop instalado ([documentação oficial](https://docs.docker.com/engine/))

## Como usar

### 1. Configuração do ambiente

Crie um arquivo `.env` no diretório raiz do projeto e preencha as informações como no exemplo abaixo:

```env
N8N_HOST="localhost"
N8N_PORT="5678"
N8N_PROTOCOL="http"

WEBHOOK_URL="http://localhost:5678/"
N8N_SECURE_COOKIE="false"
GENERIC_TIMEZONE="America/Sao_Paulo"

N8N_VOLUME_FOLDER="~/docker_volumes/n8n"
```

### 2. Iniciar o container

Execute o comando abaixo para baixar a imagem e criar o container:

```bash
docker compose up -d
```

Uma vez criado, acesse o N8N através do host configurado (no exemplo acima: `http://localhost:5678`).

### 3. Consultar logs

Para visualizar os logs do N8N em tempo real:

```bash
docker logs -f n8n
```

## Atualizando a versão do N8N

Quando houver novas atualizações disponíveis do N8N e você quiser atualizar seu container, execute os seguintes comandos:

```bash
docker compose pull
docker compose up -d
```

Estes comandos irão:
1. Buscar a versão mais recente da imagem do N8N
2. Recriar o container com a nova versão