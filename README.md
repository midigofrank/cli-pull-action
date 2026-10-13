# OpenFn GitHub Pull Action

Pulls an OpenFn project from Lightning into an `openfn.yaml` workspace using
`openfn project pull`, then commits the result to a branch. Lightning is the
source of truth: local changes to the project's files are overwritten.

Lightning's GitHub sync installs and dispatches this action for you.

> `v1` of this action uses the legacy `config.json` / `openfn pull` format.
> Pin to `@v1` if your repo still uses it.

```yaml
- name: openfn pull and commit
  uses: openfn/cli-pull-action@v2
  with:
    secret_input: ${{ secrets.OPENFN_API_KEY }}
    project_id_input: <project uuid>
    endpoint_input: https://app.openfn.org
    branch_input: main
    commit_message_input: 'Sync from Lightning'
```
