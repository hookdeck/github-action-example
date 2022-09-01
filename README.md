# Hookdeck GitHub Action Example

[slack-badge]: https://img.shields.io/badge/Slack-Hookdeck%20Developers-blue?logo=slack

[![slack-badge]](https://join.slack.com/t/hookdeckdevelopers/shared_invite/zt-yw7hlyzp-EQuO3QvdiBlH9Tz2KZg5MQ)

This repo contains an example of using the Hookdeck CLI in a GitHub action.

## Prerequisites

### Hookdeck CLI Token

You must first get a CLI token and set it as a repository or organization
secret.

Follow the [CLI installation instructions][hookdeck-cli-install] to get a local
copy of the CLI and execute the following command:

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

Copy the token from the line `api_key` and save it as a [secret in
GitHub][github-secret].

For this example it is named `HOOKDECK_CLI_KEY`

Delete the config file:

```shell
rm hookdeck.toml
```

## Create the action

See the [example workflow][example-workflow] for setting up the action.

You will see that I use a secret for my Hookdeck connection source URL since
this is a public repository but it is not necessary to make it a secret if your
repository is private.

[example-workflow]: .github/workflows/example.yml
[github-secret]:
    https://docs.github.com/en/actions/security-guides/encrypted-secrets
[hookdeck-cli-install]: https://hookdeck.com/cli#installation
