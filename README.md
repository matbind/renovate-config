# renovate-config

The shared Renovate policy for matbind's repos. A repo opts in with:

```json
{ "extends": ["github>matbind/renovate-config"] }
```

| Setting | Value | Why |
|---|---|---|
| `minimumReleaseAge` | 3 days | protects against malicious or pulled releases |
| security fixes | immediately, with no release age and no schedule | Renovate's default for vulnerability alerts; `osvVulnerabilityAlerts` covers GitLab too |
| minor + patch | one grouped PR per repo, Monday night | few PRs |
| major | its own PR, never automerged | framework majors need a person |
| lockfile maintenance | monthly, night of the 1st | transitive fixes |
| schedule | weekday nights, Europe/Vienna | PRs are ready in the morning |
| dependency dashboard | off | no issue per repo |
| automerge | off | turned on per repo only where CI runs tests |

Renovate runs self-hosted on the ops-watch watchers (heimdall for Amfortas, dssh for personal
projects). See `matbind/ops-watch`, DESIGN.md, section "Renovate".
