# Setup Oracle Instant Client

GitHub Action to download and setup [Oracle Instant Client](https://www.oracle.com/database/technologies/instant-client.html) on Linux GitHub Actions runners.

## Usage

```yaml
steps:
  - uses: ishinvin/setup-oracle-instantclient@v1
    with:
      version: "19.30.0.0.0"
```

### With custom variant

```yaml
steps:
  - uses: ishinvin/setup-oracle-instantclient@v1
    with:
      version: "23.26.1.0.0"
      variant: "basic"
```

### Using outputs

```yaml
steps:
  - uses: ishinvin/setup-oracle-instantclient@v1
    id: oracle
    with:
      version: "19.30.0.0.0"

  - run: echo "Installed to ${{ steps.oracle.outputs.oracle-home }}"
```

## Inputs

| Input     | Description                             | Required | Default     |
| --------- | --------------------------------------- | -------- | ----------- |
| `version` | Oracle Instant Client version           | Yes      |             |
| `variant` | Package variant: `basic` or `basiclite` | No       | `basiclite` |

## Outputs

| Output        | Description                                    |
| ------------- | ---------------------------------------------- |
| `oracle-home` | Path to the Oracle Instant Client installation |

## Available Versions

| Major | Example Versions              |
| ----- | ----------------------------- |
| 23.x  | `23.26.1.0.0`, `23.9.0.25.07` |
| 21.x  | `21.20.0.0.0`, `21.10.0.0.0`  |
| 19.x  | `19.30.0.0.0`, `19.11.0.0.0`  |

> ARM64 runners are only supported for version 23 or later.

## Platform

Linux runners only (Ubuntu). For self-hosted runners, ensure `curl` and `unzip` are installed.

## License

This action is licensed under the MIT License.

Oracle Instant Client is proprietary software owned by Oracle Corporation. By using this action, you agree to the [Oracle Free Use Terms and Conditions](https://www.oracle.com/downloads/licenses/oracle-free-license.html). Oracle Instant Client is downloaded directly from Oracle's official distribution site.
