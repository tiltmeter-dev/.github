# Tiltmeter

**An early-warning system for the third-party APIs your AI agents depend on, with the fix as a pull request.** · [tiltmeter.dev](https://tiltmeter.dev)

Tiltmeter learns the shape of the APIs your code calls, notices when a provider renames a
field, starts sending `null` or removes an endpoint, and hands the change to an agent that
adapts your code and opens the pull request. In provider mode, API providers publish signed
change notices and every affected repository gets its fix.

| Repository | What it is |
|---|---|
| [tiltmeter](https://github.com/tiltmeter-dev/tiltmeter) | The CLI, the MCP server, `tiltmeter fix` and provider mode. `pip install tiltmeter` |
| [tiltmeter-action](https://github.com/tiltmeter-dev/tiltmeter-action) | The GitHub Action: fail CI on drift, or open the fix when a provider changes its API |
| [website](https://github.com/tiltmeter-dev/website) | [tiltmeter.dev](https://tiltmeter.dev), including the [guide for API providers](https://tiltmeter.dev/providers/) |
| [demo-stripe-billing](https://github.com/tiltmeter-dev/demo-stripe-billing), [demo-github-pulse](https://github.com/tiltmeter-dev/demo-github-pulse), [demo-claude-triage](https://github.com/tiltmeter-dev/demo-claude-triage) | Clients written for older versions of the Stripe, GitHub and Anthropic APIs, each with the pull request Tiltmeter opened against the current spec |

### Why there are forks here

Each fork carries a fix that Tiltmeter generated for a public project after its API
provider changed something, and its pull request is open in the original repository. The
first was [Stripe's own subscription sample](https://github.com/stripe-samples/subscription-use-cases/pull/1229),
which no longer type-checks against Stripe's SDK since API version 2025-03-31.
[All the pull requests](https://github.com/search?q=%22generated+automatically+by+Tiltmeter%22+is%3Apr+-org%3Atiltmeter-dev&type=pullrequests)
are public. We delete a fork once its pull request is merged or closed.
