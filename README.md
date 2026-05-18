# **Action Library Generate Changelog**

| **Home**
| [Changelog](./CHANGELOG.md)
| [Contributing](./CONTRIBUTING.md)
| [Tech Doc](./techdoc.md)
| <!-- End Of Menu -->

---

Builds `CHANGELOG.md` from `logs/<version>.md` files, scoped to the VERSION file(s) affected by a PR.

## Behavior

- Root `VERSION` produces a root `CHANGELOG.md`.
- Feature VERSION files produce `feature/CHANGELOG.md`.
- Supports log ranges: `all`, `latest`, or a starting version (e.g., `1.2.3`).
- Accepts log filenames and `source_range` values with optional leading `v`.
- Skips when only `*.md` or `.github/*` files are changed.
- Commits changelog updates; pushes pending commits by default (set `push_changes=false` to skip).

## Inputs

| Name | Required | Description |
| --- | --- | --- |
| `pr_number` | No | PR number used to discover affected VERSION files. |
| `github_token` | No | GitHub token for API access (defaults to `GITHUB_TOKEN`). |
| `version_file` | No | Preferred VERSION file path (optional). |
| `release_version` | No | Deprecated. Version is derived from log files. |
| `source_range` | No | `all`, `latest`, or a starting version (default: `all`). |
| `push_changes` | No | Push commits to the remote (default: `true`). |

## Changelog Header

Root:

```md
# **<repo_title>** | Changelog
```

Feature:

```md
# **<repo_title>** | <feature_name> | Changelog
```

---

<p style="text-align: center;"><a href="#">Return to Top</a></p>

<h6 style="text-align: center;">Copyright &copy; Technolog Ltd</h6>
