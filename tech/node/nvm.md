# nvm - node version manager

Firstly, [install nvm](https://github.com/nvm-sh/nvm#installation-and-update).


Then install latest node version by running:

`nvm install node`

To install any specific node version,(say `8.9.1`) run:

`nvm install 8.9.1`

To use a particular version of node, run:

`nvm use 8.9.1`.

To list all available node versions (locally and remotely):

`nvm ls`
`nvm ls-remote`



Create a `.nvmrc` file in the root of the project, to specify the node version to use for a project.

`echo node -v > .nvmrc`


---
[ref](https://github.com/nvm-sh/nvm)