# Relay Git review

Inspect tracked file status, staged changes and unstaged changes within the approved directory.

## Status and compatibility

Experimental native-tool package. Requires the Relay build that implements
the `tool` contribution and the matching `relayd plugin` helper. Older Relay
builds reject this package safely. This is a data-only package: the implementation
lives in [Relay](https://github.com/genomewalker/relay-terminal), not executable
code downloaded from this repository. No install hooks or background polling.

The native implementation is under development and has not yet passed installed-app
acceptance. Do not mistake a manifest for a production-ready extension.

## Install and use

When a tagged release is available, open Relay Settings → Plugins, enter
`genomewalker/relay-plugin-git-review` and its exact tag, review the digest and
permissions, install disabled, then Enable. Select a terminal pane and open
the puzzle-piece button in the workspace toolbar. Select this tool, verify the
host/directory, and choose **Allow once & refresh**. Each refresh is explicit.

Updates require another reviewed version and start disabled. Disable, Roll back
and Uninstall are available in Settings. Safe mode suppresses all plugin tools.

## Limits

Read-only. No staging, commits, untracked file contents, or agent handoff. Git output is bounded to 1 MiB per command and external diff/textconv are disabled.

Only the captured pane/host/directory is used; switching tabs does not retarget
an in-flight request. Remote hosts need a matching helper installed through Relay's
existing approved setup flow. Agent processes are never restarted by this plugin.

## Package verification

```sh
python3 -m json.tool relay-plugin.json
```

Runtime, path-containment, payload-integrity and permission tests live alongside
the implementation in Relay. Publish `relay-plugin.json` as a release asset only
after those tests and the corresponding installed-app acceptance checks pass.

## License

No license has been selected yet. Public visibility does not grant a reuse license.
