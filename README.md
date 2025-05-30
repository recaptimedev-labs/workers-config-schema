# Cloudflare Workers config schema

[![nightly schema generator](https://github.com/recaptimedev-labs/workers-config-schema/actions/workflows/config-schema-generator.yml/badge.svg)](https://github.com/recaptimedev-labs/workers-config-schema/actions/workflows/config-schema-generator.yml)

Andrei Jiroh of Recap Time Squad is maintaining this repository (via a GitHub Actions workflow that runs nightly)
by generating the config schema for Cloudflare Workers against the [Workers SDK repository][repo]'s main branch,
so that you can use the generated JSON schema on your TOML or JSON config without needing to run `npm I wrangler`.

## Usage

Install [Even Bettet TOML VS Code extension][ext] and add this line at the top of your `wrangler.toml` file:

```toml
$schema = "https://raw.githubusercontent.com/recaptimedev-labs/workers-config-schema/refs/heads/main/config-schema.json"
# rest of the config go here
```

Alternatively on your `wrangler.json(c)` file:

```jsonc
{
  "$schema": "https://raw.githubusercontent.com/recaptimedev-labs/workers-config-schema/refs/heads/main/config-schema.json"
  // rest of the config go here
}
```

[repo]: https://github.com/cloudflare/workers-sdk
[ext]: https://marketplace.visualstudio.com/items?itemName=tamasfe.even-better-toml#completion-and-validation-with-json-schema
