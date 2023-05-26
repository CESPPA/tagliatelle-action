# tagliatelle-action

### GitHub action for [/tagliatelle](https://github.com/cesppa/tagliatelle)

Utility to update tags and version numbers in project files. Useful for config files, kustomize projects, and helm
charts.

## Inputs

| Input   | Required | Description                                                      |
|---------|----------|------------------------------------------------------------------|
| user    | yes      | github username                                                  |
| token   | yes      | github personal access token                                     |
| repo    | yes      | repo that contains target file (access and permissions required) |
| file    | yes      | target file to update                                            |
| tag     | yes      | string to use as replacement                                     |
| pattern | yes      | regex pattern to use                                             |

## Example usage

```yaml
<<<<<<< Updated upstream
uses: xlyk/tagliatelle@v2
=======
uses: cesppa/tagliatelle@main
>>>>>>> Stashed changes
with:
  user: 'your-username'
  token: "${{ secrets.GH_ACTIONS_ACCESS_TOKEN }}"
  repo: 'https://github.com/cesppa/tagliatelle.git'
  file: 'sample.yaml'
  tag: '1.0.0.1'
  pattern: '(app1"\n.*newTag: ")(.*?)(")'
```
