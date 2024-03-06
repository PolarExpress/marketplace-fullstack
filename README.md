# marketplace-fullstack

This repository contains the frontend and backend for the GraphPolaris marketplace.

## Development setup

### Requirements
- VS Code
- VSC Dev Containers extension
- `docker` and `docker-compose` (or Docker Desktop + WSL for Windows systems)

### Steps
1. Clone this repository and its submodules using

   ```sh
   git clone git@github.com:PolarExpress/marketplace-fullstack.git --recurse-submodules
   ```
2. Open the root folder in VS Code. Make sure you've installed the Dev Containers extension.
3. Go into the dev container (F1 -> Dev Containers: Reopen in Container)
4. Inside the dev container, run npm install for both the frontend and backend package:
   
   ```sh
   npm --prefix backend i && npm --prefix frontend i 
   ```

### `node_modules` and the Dev Container
Because of performance issues with bind volumes on Windows, the `node_modules` folders are inside their own volumes managed by Docker. If you ever need to remove this folder, do it by running the following command in the Dev Container:

```sh
# make sure to cd to the frontend/backend repo before running this command
rm -rf node_modules/*
```

This will not remove the folder itself; this is impossible due to the fact that it appears as a mounted device to the container system.

This also means `npm install` needs to be run again after a docker volume/system prune.

### Accessing the database from the host system

The PostgreSQL database is autostarted by the dev container. To access the database from the host, add the following to `.devcontainer/devcontainer.json`:

```json
"forwardPorts": ["5432"]
```

This will expose the Postgres instance on port 5432.

### Running the frontend/backend
For details on how to run the frontend or backend, refer to the README.md file in the corresponding repository.

## Deployment

### Requirements
- `docker` and `docker-compose` (or Docker Desktop + WSL for Windows systems)
- optional: `docker-buildx` (for more efficient multi-stage builds)

### Steps
To deploy the entire stack, simply run
```
docker compose up -d
```
in the root directory of this repo.

If instead you only need the backend + DB, run:
```
docker compose up -d backend
```



