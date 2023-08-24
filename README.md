#OpenFN Github Deploy Action 

This action deploys to a specific Lightning instance whenever it is invoked.

It depends on an repository containing the following

1. A `state.json` file which details ids and jobs in a project
2. A `project.yaml` file detailing a project its workflows, edges and triggers 
3. A `config.json` file detailing a connection to a Lightning instance

Additionally one needs to pass in their OPENFN API KEY to the action as an input best way to do this would be through 
an input. The required key is `secret_input`

See an example project structure [here](https://github.com/OpenFn/dummy-deploy-test)

An example of how to use this action in workflow 
```
on:
  push:
    branches:
      - main

jobs:
  deploy-to-lightning:
    runs-on: ubuntu-latest
    name: Deploy this project to OpenFn/Lightning
    steps:
      - name: Deploy to Lightning
        uses: openfn/deploy-action@v0.1.9 
        with: 
          secret_input: ${{ secrets.OPENFN_API_KEY }}
```

