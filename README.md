# marketplace-fullstack

This repository contains the frontend and backend for the GraphPolaris marketplace.

The dev container can be used for creating a development environment for working on and testing both frontend and backend at the same time.  
For this, the Dev Containers extension needs to be installed.

## Notes

- When first cloning the repository, make sure to use `git clone --recurse-submodules`, and use `npm install` in both the frontend and the backend folders.
- You also need to rerun `npm install` when the the dependencies changed.
- When you want to clear the `node_modules` folder, **do not** remove the folder. Instead, clear the contents using `rm -rf node_modules/* node_modules/.*`.
- The contents of the `node_modules` folder live inside of the dev container, but an empty folder will be created locally. This is expected.
