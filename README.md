Keygen.sh docker compose example
===============================
This is a simple example of how to use the keygen.sh docker image with docker compose.

## Usage
1. Clone this repository
1. Run `docker-compose up -f docker-compose-db.yml -d` to init the database and redis
1. Run to setup environment
```
docker run --rm -it -e SECRET_KEY_BASE="$(openssl rand -hex 64)" \
  -e ENCRYPTION_DETERMINISTIC_KEY="$(openssl rand -base64 32)" \
  -e ENCRYPTION_PRIMARY_KEY="$(openssl rand -base64 32)" \
  -e ENCRYPTION_KEY_DERIVATION_SALT="$(openssl rand -base64 32)" \
  -e DATABASE_URL="postgres://postgres:postgres@host.docker.internal:5432/postgres" \
  -e REDIS_URL="redis://host.docker.internal:6379" \
  -e KEYGEN_HOST="api.keygen.localhost" \
  -e KEYGEN_MODE="singleplayer" \
  -e KEYGEN_EDITION="CE" \
  keygen/api setup
```
1. Copy .env.template to .env
1. Run `docker-compose up -d` to start the keygen.sh server
1. Try the api.rest in vscode to test the server