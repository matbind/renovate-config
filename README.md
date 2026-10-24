# renovate-config

The shared Renovate policy for matbind's repos. The settings themselves, each with its reason,
are in the JSON files; this page only says which preset to pick.

| Preset | Use for | Extends with |
|---|---|---|
| [`default.json`](default.json) | repos with CI that runs the tests | `{"extends": ["github>matbind/renovate-config"]}` |
| [`security-only.json`](security-only.json) | repos without CI or active development | `{"extends": ["github>matbind/renovate-config:security-only"]}` |

The idea behind `default.json`: few PRs, and none that need attention by surprise. New releases
wait 3 days, security fixes don't wait. Minor and patch updates come as one weekly PR. Majors
open only after approval in the repo's dependency dashboard issue. Nothing is merged
automatically unless a repo turns it on for itself.

Renovate runs self-hosted in GitHub Actions, one runner repo per area (`renovate-personal`,
`renovate-amfortas`). A repo is managed only once its onboarding PR is merged.
