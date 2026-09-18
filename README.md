# Relay git review

Inspect project changes, diffs and worktrees and hand selected context to an existing agent.

## Status

Development scaffold. This repository currently contains the implementation plan,
not a functional plugin. There is no installable release or remote helper.

[Relay](https://github.com/genomewalker/relay-terminal) currently has an experimental
declarative plugin installer. The scoped broker, permissions and runtime required
for this integration must be implemented and verified before release. This plugin
does not currently perform the operations described above.

## Planned implementation

- [ ] Define bounded read-only Git status and diff operations.
- [ ] Preserve source host/project/worktree identity in every action.
- [ ] Require explicit selection and destination for agent handoff.
- [ ] Test renamed, untracked and deleted files, large diffs and concurrent edits; no implicit staging or commits.

## Installation

Not available yet. Do not install a repository checkout as a plugin or run scripts
from it. Once the required Relay API exists and acceptance checks pass, tagged
GitHub releases will provide the supported package and compatibility information.
No placeholder release is published merely to make the installer show this plugin.

## Safety and release requirements

- Terminal input, rendering, SSH and recovery remain core-owned and independent.
- Access is scoped to the selected project and host; no ambient credentials.
- Activate only when needed. Bound requests, output, memory and background work.
- Test permission denial/revocation, cancellation, disconnects and incompatible workers.
- Publish installation, update, rollback and removal instructions with the first working release.
- Verify the installed UI manually as well as running automated tests.

## Contributing

Open an issue to discuss the protocol and scope before implementing remote helpers.
Keep changes focused and include tests. Do not include credentials, private hostnames,
terminal transcripts or user project data in issues or fixtures.

## License

No license has been selected yet. Public visibility does not grant a reuse license.

