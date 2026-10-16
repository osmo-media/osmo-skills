# Osmo skills

Give a coding agent Osmo: an animation language with its own renderer, a creative
toolkit, and a review workflow, all behind one CLI.

- **Make motion graphics as editable code.** Animated titles, lower thirds,
  kinetic typography, logo animations, overlays, product shots on 3D devices, and
  video compositions, previewed and rendered locally without an account.
- **Generate and process media on Osmo.** Video, images, speech, sound effects,
  and music from models such as Seedance, Grok, Nano Banana, and GPT Image, plus
  background removal for images and video and raster-to-SVG vectorizing. They
  run on Osmo's servers against your account, which includes a free monthly
  allowance.
- **Use your own tools.** Shaders and ready-made 3D models from the catalog, and
  images, footage, audio, fonts, and GLB models from Blender or any other tool.
- **Share any video for review.** An H.264 MP4 from any tool goes on a review link
  with timestamped comments, no Osmo project needed. Ask the agent to apply the
  feedback and publish the next version to the same link.

One compact skill covers all of it. The CLI supplies the detailed project
instructions and API declarations for its installed version.

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

Ask for the result you want, for example: “Make a five-second title animation,”
“Put our app on an iPhone,” “Remove the background from this clip,” “Generate a
sound effect for the logo hit,” “Share this video for feedback,” or “Apply the
open review comments.” Agents that support automatic skill selection can discover
Osmo without its name in the request. To select it explicitly:

- **Claude Code:** `/osmo Make a five-second title animation.`
- **Codex CLI / IDE:** `$osmo Make a five-second title animation.`, or select it
  through `/skills`.
- **Other hosts:** select the `osmo` skill using that host's skill interface.

Invocation syntax belongs to the host. See the official
[Codex](https://learn.chatgpt.com/docs/build-skills) and
[Claude Code](https://code.claude.com/docs/en/skills) documentation.

## Run the CLI

Installing the skill does not install the CLI. The skill uses an existing
compatible `osmo` installation or runs the package through `npx`. To start without
a global install:

```sh
npx -y @osmo.inc/cli@latest studio init my-animation
cd my-animation
```

For repeated commands, use the same resolved CLI version throughout the task.
For regular use, a global install is also available:

```sh
npm install -g @osmo.inc/cli
osmo studio init my-animation
cd my-animation
```

These are alternative ways to start a project. Invoke the skill inside that
folder with your animation brief. It reads the generated project guide and scene
declarations, then checks, previews, and renders the animation. In an existing
project, invoke it from that project instead.

Local work needs no account login. Studio supports Apple Silicon macOS and Linux
x64/arm64 (glibc). It requires Node.js 22 or later and Git 2.29 or later; video
rendering needs FFmpeg/ffprobe. Run the installed CLI's `--help` for current
requirements and commands.

## Share, get feedback, and work together

Ask the agent to share a video. After sign-in, it can publish an H.264 MP4, from
any tool, on a review link where people comment on specific moments; no Osmo project
is needed. For an Osmo project it publishes the project itself, so comments can
also point at areas and layers. Ask it to apply the feedback, check the result,
and publish an updated version to the same link.

If someone should work on the video with you, ask the agent to give that person
access. They can get their own editable copy, make changes, and publish updates
to the same link. Sharing for feedback does not automatically grant editing access.

You can also ask the agent to check for new comments and apply fixes automatically
for an agreed period. This needs a running agent or scheduling support in its host;
the CLI itself does not provide a continuous comment watcher.

## License

The files in this repository are MIT licensed. This license does not cover or
distribute the proprietary Osmo CLI, renderer, or resource packages.
