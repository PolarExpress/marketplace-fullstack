# marketplace-fullstack

This repository contains the frontend and backend for the GraphPolaris marketplace.

## Development setup

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

### Accessing the database from the host system

The PostgreSQL database is autostarted by the dev container. To access the database from the host, add the following to `.devcontainer/devcontainer.json`:

```json
"forwardPorts": ["5432"]
```

This will expose the Postgres instance on port 5432.

### Running the frontend/backend
For details on how to run the frontend or backend, refer to the README.md file in the corresponding repository.

