# setup-ssh
Github Action for setting up a SSH credential stored in a secret

## Example

The simplest usage possible:

```yml
steps:
  - name: Set up SSH credentials
    with:
      ssh-key: ${{ secrets.SSH_KEY }}
```

If you stored the key using base64 encoding:

```yml
steps:
  - name: Set up SSH credentials
    with:
      ssh-key: ${{ secrets.SSH_KEY }}
      b64-enc: true
```

## Inputs:

| Variable | Description | Default value | Required |
| - | - | - | - |
| ssh-key | Your SSH credential content | None | Yes
| b64-enc | Boolean representing if the `ssh-key` is encoded using Base64 | False | No |
| target-file | Target file to write the content from `ssh-key` | `$HOME/.ssh/id_ed25519` | False | No |
| create-path | Whether it should create `target-file` parent directories | True | No |

## Outputs:

| Variable | Description |
| - | - |
| ssh-key-path | Directory path to where the SSH credentials were stored |
