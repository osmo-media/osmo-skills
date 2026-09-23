# Osmo skills

A small, public skill that directs coding agents to the Osmo CLI.
The CLI supplies project instructions and API declarations for its installed
version. This repository contains only the skill and installation guidance.

## Install the skill

For Codex and Claude Code, available across projects:

```sh
npx skills add osmo-media/osmo-skills --skill osmo -g -a codex -a claude-code
```

For another supported harness, use the interactive installer:

```sh
npx skills add osmo-media/osmo-skills --skill osmo -g
```

Omit `-g` to install only in the current project. See the
[skills installer](https://github.com/vercel-labs/skills) for supported agents.
The skill uses the [Agent Skills format](https://agentskills.io/specification).

## Use it

- **Claude Code:** `/osmo Make a five-second title animation.`
- **Codex CLI / IDE:** `$osmo Make a five-second title animation.`, or select it
  through `/skills`.
- **Other hosts:** select the `osmo` skill using that host's skill interface.

Invocation syntax belongs to the host. See the official
[Codex](https://learn.chatgpt.com/docs/build-skills) and
[Claude Code](https://code.claude.com/docs/en/skills) documentation.

## Install the CLI

The skill is public; the CLI is currently private. Installing the skill does not
install the CLI or grant package access. Request access from your Osmo contact.

The current CLI build requires macOS on Apple Silicon, arm64 Node.js 22, npm,
and FFmpeg/ffprobe on `PATH`.

Once your npm account has read access to `@osmo.inc/cli`:

```sh
npm login
npm install -g @osmo.inc/cli
osmo --help
```

You can also use `npx @osmo.inc/cli` as the command prefix, or install a private
CLI archive supplied by Osmo. npm package access is separate from `osmo login`.
If npm denies access, sign in with an authorized account or request package access.

For a new animation project:

```sh
osmo init my-animation
cd my-animation
```

Then invoke the skill with your animation brief. It reads the generated
`AGENTS.md` and installed scene declarations, keeping its guidance aligned with
your CLI version. In an existing project, invoke it from that project instead.

## License

The files in this repository are MIT licensed. This license does not cover or
distribute the private Osmo CLI, renderer, or resource packages.
