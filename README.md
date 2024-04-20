Keygen.sh docker compose example
===============================
This is a simple example of how to use the keygen.sh docker image with docker compose.

You need to have docker and docker compose >v2.24.0 installed in your system.

## Usage
1. Clone this repository
2. Run `docker compose run init` (or `docker compose run --build init` if you update the repo) to generate the keys and account id. If you have problems when running the command, please make sure docker compose >v2.24.0 is installed in your system.
3. Run `docker compose run setup` to setup the keygen.sh environment
4. Set the user name and password you used in your environment
```bash
# Linux
export KEYGEN_ADMIN_USER=me@email.com
export KEYGEN_ADMIN_PASS=password123
```
5. Run `docker compose up --scale setup=0 --scale init=0` to start the keygen.sh server
6. Copy the certificates to the certificates folder. You should import the certificates to your system to avoid the security warning in the browser
```docker cp keygen-docker-compose-caddy-1:/data/caddy/pki ./certificates```
7. Try the api.rest in vscode to test the server
