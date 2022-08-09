# Hookdeck GitHub Action Example

This repo contains an example of using the Hookdeck CLI in a GitHub action.

## Prerequisites

### Hookdeck CLI Token

You must first get a CLI token and set it as a repository or organization secret.

Follow the [CLI installation instructions][hookdeck-cli-install] to get a local copy of the CLI and execute the following command:

```shell
hookdeck login --config hookdeck.toml
```

Now examine the config file:

```shell
cat hookdeck.toml
```

It will look something like this:

```toml
[default]
  api_key = "1234567910..."
  client_id = "cli_123"
  device_name = "MacBook-Pro.local"
  display_name = "Lee Trout"
  team_name = "Demo"
```

Copy the token from the line `api_key` and save it as a [secret in GitHub][github-secret].

For this example it is named `HOOKDECK_CLI_KEY`

Delete the config file:

```shell
rm hookdeck.toml
```

## Create the action

Add a step to install the Hookdeck CLI (assumes Ubuntu runner):

```shell
TODO
```

Add a step to run the CLI in the background

```shell
hookdeck listen <address> <source-name>
```

For example, to forward requests for my source named `action-demo` to port 9090:

```shell
hookdeck listen 9090 action-demo
```

[github-secret]: https://docs.github.com/en/actions/security-guides/encrypted-secrets
[hookdeck-cli-install]: https://hookdeck.com/cli#installation
