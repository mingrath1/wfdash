# wfdash

A local, read-only browser dashboard for your wayfinder maps on GitHub. View your maps as a dependency graph and see which tickets are ready to start.

## Recovered source

This repository restores the source published as [`@mingrath/wfdash@0.1.5`](https://www.npmjs.com/package/@mingrath/wfdash/v/0.1.5) on August 2, 2026. The original `mingrath/wfdash` repository is no longer available.

The application code, package metadata, skills, hooks, and MIT license are unchanged from that npm release. The original README is preserved in [`docs/README.npm-0.1.5.md`](docs/README.npm-0.1.5.md).

Git history, tests, screenshots, and the Claude Code marketplace manifest were not included in the npm archive. They have not been reconstructed. The original README contains historical links and plugin instructions that depend on those missing files.

## Run from this repository

You need Node.js 18 or newer and an authenticated [GitHub CLI](https://cli.github.com/). There are no npm dependencies and no build step.

```sh
git clone https://github.com/mingrath1/wfdash.git
cd wfdash
gh auth login
node bin/wfdash.js
```

The command starts the dashboard at `http://127.0.0.1:7777` and opens your browser. Set `WFDASH_NO_BROWSER=1` to print the URL without opening a browser.

Open a specific map or stop the server with these commands:

```sh
node bin/wfdash.js owner/repo#12
node bin/wfdash.js stop
```

## Install the published npm package

The existing package still uses the original `@mingrath` namespace. This repository restoration does not publish a new npm version.

```sh
npm install -g @mingrath/wfdash@0.1.5
wfdash
```

Run `wfdash install` to install the bundled agent skills. That command writes skills into supported user-level agent directories.

## Find your maps

Maps are GitHub issues labelled `wayfinder:map`, with tickets as sub-issues and blockers as native issue dependencies. The overview searches repositories owned by the account authenticated through `gh`.

To include an organization's maps, set a search query before starting the dashboard:

```sh
WFDASH_SEARCH='label:"wayfinder:map" state:open org:acme' node bin/wfdash.js
```

The server binds to `127.0.0.1` only. It uses your existing `gh` authentication and does not send your token to the browser. It does not write to GitHub.

## License

[MIT](LICENSE). Original authorship is preserved.
