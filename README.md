# Send to ZPMHUB

GitHub action to send your package to ZPMHUB.

## Customizing

### Inputs

The following inputs can be used as `step.with` keys

| Name             | Type    | Description                        |
|------------------|---------|------------------------------------|
| `token`          | String  | apikey token of zpmhub (required) |
| `repository` | String | repository of your project (required)|
| `url` | String | host of zpmhub `https://zpmhub/api` (required)|

## Example usage

Create `.github/workflow/send.yaml` with the following to send on push.

```yaml
on:
  push:
    branches:
      - "master"
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
    - uses: banksiaglobal/send-to-zpmhub
    - name: Send ${{ github.repository }} to ZPMHUB
      with:
        token: ${{ secret.token }}
        repository: ${{ github.repository }}
        url: ${{ secret.url }}
```


## License
The scripts and documentation in this project are released under the [MIT License](https://github.com/banksiaglobal/send-to-zpmhub/blob/main/LICENSE).