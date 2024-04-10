Keygen.sh docker compose example
===============================
This is a simple example of how to use the keygen.sh docker image with docker compose.

## Usage
1. Clone this repository
2. Run `docker compose run init` (or `docker compose run --build init` if you update the repo) to generate the keys and account id
3. Run `docker compose run setup` to setup the keygen.sh environment
4. Set the user name and password you used in your environment
```bash
# Linux
export KEYGEN_ADMIN_USER=me@email.com
export KEYGEN_ADMIN_PASS=password123
```
5. Run `docker compose up --scale setup=0 --scale init=0` to start the keygen.sh server
6. Try the api.rest in vscode to test the server
