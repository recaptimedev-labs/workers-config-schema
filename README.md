# Nightly generated Cloudflare Workers config schema

[![nightly schema generator](https://github.com/recaptimedev-labs/workers-config-schema/actions/workflows/config-schema-generator.yml/badge.svg)](https://github.com/recaptimedev-labs/workers-config-schema/actions/workflows/config-schema-generator.yml)

[Andrei Jiroh](https://github.com/ajhalili2006) of [Recap Time Squad](https://recaptime.dev) is maintaining this repository
(via a [GitHub Actions workflow][workflow] that runs nightly at midnight UTC) by generating the config schema for Cloudflare Workers
against the [Workers SDK repository][repo]'s main branch, so that you can use the generated JSON schema on your TOML or JSON config
without needing to run `npm i wrangler` locally, which is good for those editing via VS Code for Web without compute access.

## Should I use this instead of the one shipped on `wrangler` npm package?

Depends on whether you edit your Wrangler configs via VS Code for Web, regardless of whether you use features that
require compute (i.e. terminal and extensions that need local filesystem access and system binaries).

Note that this also works on other editors that support loading custom JSON schemas, although I have yet to find any
plugins/support outside VS Code for custom TOML schemas, but please let me know in the issue tracker.

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

## License

Since the upstream project adopts a dual-licensing model under both MIT and Apache licenses, we chose to license
this repository's contents under the former to simplify license compliance.

[repo]: https://github.com/cloudflare/workers-sdk
[ext]: https://marketplace.visualstudio.com/items?itemName=tamasfe.even-better-toml#completion-and-validation-with-json-schema
[workflow]: .github/workflows/config-schema-generator.yml
