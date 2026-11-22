# CS — My Claude setup (skills, plugins, connectors)

Backup of my custom Claude skills and the list of plugins/connectors they depend on,
so I can restore the whole video-production workflow anywhere.

## Layout
- `skills/` — my own skills. Each folder = one skill (`SKILL.md` + helpers).
  - `video-studio` — **master orchestrator** for short-form (9:16) video; conducts the rest
  - `motionmaxxing` — motion-graphics direction + build
  - `earshot` — judge/choose/verify sound
  - `video-style-extractor` — extract a reference video's style profile
  - `video-making` — pre-flight skill before making a new video
  - `brag` — project/URL → short launch video
- `plugins.md` — plugins to install (youtube-agent, remotion, ffmpeg-llm, ...)
- `connectors.md` — connectors to reconnect and which skill uses them
- `.env.example` — names of keys needed (no real values)

## Restore on a new account / machine
1. Clone this repo.
2. Skills: zip each folder in `skills/` and upload at Claude → Settings → Capabilities → Skills
   (Claude Code: copy the folders into `~/.claude/skills/`).
3. Install the plugins listed in `plugins.md`.
4. Reconnect the connectors listed in `connectors.md`.
5. Copy `.env.example` to `.env` and fill in your keys (never commit `.env`).

The master skill `video-studio` works best when all sub-skills, plugins and connectors are present;
if one is missing it uses a fallback and says so in its hand-off note.
