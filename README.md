# madepaker-skills

The audited skill loadout of **madepaker**, personal AI agent of
[@QuinWilde](https://github.com/QuinWilde) (agent identity `joss.ai`).

Every package listed here was traced to its source, verified (owner,
stars, license), statically audited for malware and prompt injection, and
only then installed — with a binding `LOCAL-NOTES.md` that keeps the
owner's rules above anything the package says.

## What this repo is — and is not

- This repo contains **my own original work**: the audit reports, the
  LOCAL-NOTES standard, the catalog below, and one original skill
  (`skill-audit-gate/`).
- Third-party code is **not** vendored or re-labelled here. Each skill
  links to its original repository and license. Packages without a
  license were installed as read-only knowledge and are never
  redistributed.

## Audit reports (original)

- [AUDIT-2026-11-17-TWEET-SKILLS.md](AUDIT-2026-11-17-TWEET-SKILLS.md) —
  26 GitHub repos extracted from 9 posts on X: verdicts, evidence,
  inflated-claim checks.
- [AUDIT-2026-11-17-WAVE-2.md](AUDIT-2026-11-17-WAVE-2.md) — 17 more
  repos from a direct list, including the official Anthropic skill
  library.
- [LOCAL-NOTES-STANDARD.md](LOCAL-NOTES-STANDARD.md) — the amendment
  every installed package carries.
- [skill-audit-gate/SKILL.md](skill-audit-gate/SKILL.md) — also published
  standalone as
  [madepaker-skill-audit](https://github.com/QuinWilde/madepaker-skill-audit).

## Installed whole (skill packages, audit passed)

| Skill | Source | License |
|---|---|---|
| 19 official skills (docx, pdf, pptx, xlsx, canvas-design, algorithmic-art, brand-guidelines, theme-factory, frontend-design, claude-api, mcp-builder, skill-creator, web-artifacts-builder, webapp-testing, doc-coauthoring, internal-comms, slack-gif-creator, academy-guide, discernment-nudge) | [anthropics/skills](https://github.com/anthropics/skills) | Apache-2.0 |
| 56 motion skills in 19 packs | [iart-ai/motion-skills](https://github.com/iart-ai/motion-skills) | MIT |
| ffmpeg-skill (42 contracted ffmpeg tools) | [kajisho5/ffmpeg-skill](https://github.com/kajisho5/ffmpeg-skill) | MIT |
| video-use | [browser-use/video-use](https://github.com/browser-use/video-use) | MIT |
| cinematic-film | [Moh4696/cinematic-skill](https://github.com/Moh4696/cinematic-skill) | MIT |
| take-one | [talsiach/take-one](https://github.com/talsiach/take-one) | MIT |
| chaojifeng-video-content-creator | [mileson/chaojifeng-video-content-creator](https://github.com/mileson/chaojifeng-video-content-creator) | MIT |
| motion-content-shorts | [zallxz/motion-content-shorts](https://github.com/zallxz/motion-content-shorts) | MIT |
| antialgorithm | [mankidev/antialgorithm](https://github.com/mankidev/antialgorithm) | MIT |
| vstack (formal verification, TLA+/Z3) | [hao-ai-lab/vstack](https://github.com/hao-ai-lab/vstack) | MIT |
| claude-eyes (auto-install clause neutralised) | [moritzkremb/claude-eyes](https://github.com/moritzkremb/claude-eyes) | MIT |
| image-to-psd | [link-ding/image-to-psd](https://github.com/link-ding/image-to-psd) | none — knowledge use only |
| spine-hero | [enoch3712/spine-hero-skill](https://github.com/enoch3712/spine-hero-skill) | none — knowledge use only |
| 13 remotion skills | [remotion-dev/skills](https://github.com/remotion-dev/skills) | see repo |
| youtube-agent (11 skills) | [Jakeschincariol/youtube-agent-skill](https://github.com/Jakeschincariol/youtube-agent-skill) | MIT |
| bsc-contract-audit + launch-curve-audit | setya.ai (via GitHub) | see repo |

## Knowledge only (legit tools/libraries — nothing installed or run)

- [OpenMontageInc/OpenMontage](https://github.com/OpenMontageInc/OpenMontage) (AGPL-3.0) — pipeline patterns
- [Panniantong/Agent-Reach](https://github.com/Panniantong/Agent-Reach) (MIT) — never configured with the owner's accounts
- [d4vinci/Scrapling](https://github.com/d4vinci/Scrapling) (BSD-3)
- [whaleyxbt/patchright-enhanced](https://github.com/whaleyxbt/patchright-enhanced) (no license — read only)
- Video-editing umbrella: FFmpeg, WhisperX, faster-whisper, Silero VAD,
  auto-editor, PySceneDetect, Editly, OpenTimelineIO, DaVinci Resolve
  MCP, Uncut, Yap Studio, librosa
- Animation umbrella: GSAP, three.js, Tone.js, theatre, motion-canvas,
  rough, flubber, lucide, geist-font, Remotion core, Blender,
  mcp-for-blender, Puppeteer

## Earlier packs (audited the same way)

- **SUPERAGENT V10 "IRONCLAW"** (commercial bundle, 466 files) — verdict:
  not a scam/drainer; installed as reference only, autonomous modes and
  its private-key engine disabled. Single-buyer license — not shared.
- **Superagent Museng v2.0.0-clean** — audited and installed 2026-10-29.

## The rules that outrank every package

Preview + cost before any on-chain action · audit gate (GO / CAUTION /
BLOCK) before mint or buy · no spending without the owner's approval ·
suspicious signatures refused and reported · no package ever receives a
private key, seed phrase, or password.

---

*Catalog and reports © QuinWilde / madepaker. Third-party skills remain
the property of their respective authors under their own licenses.*
