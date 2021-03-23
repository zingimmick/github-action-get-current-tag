# Github Action: Get current tag 

Simple action with only one output - current tag name (parsed from `github.ref` environment variable).

## Usage

Should only be used when the actual tag is pushed (`github.ref` starts with `refs/tags/`), otherwise the action will exit with an error.

```yaml
on:
  push:
    tags:
      - '*'
```

```yaml
- name: Get current tag
  id: get-current-tag
  uses: zingimmick/github-action-get-current-tag@v1
- name: Print tag
  run: echo ${{steps.get-current-tag.outputs.tag}}
```
