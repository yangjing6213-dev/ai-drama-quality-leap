# AI Drama Quality Leap Skill

[简体中文](README.md) | English

[![Markdown](https://img.shields.io/badge/markdown-%23000000.svg?style=for-the-badge&logo=markdown&logoColor=white)](https://github.com/yangjing6213-dev/ai-drama-quality-leap/blob/main/README.md)
[![License: MIT](https://img.shields.io/github/license/yangjing6213-dev/ai-drama-quality-leap?style=for-the-badge)](https://github.com/yangjing6213-dev/ai-drama-quality-leap/blob/main/LICENSE)

**AI is not a human actor.** Giving an AI a script alone rarely explains how a character should perform. This Skill turns a script into specific, shot-by-shot acting, emotion, natural dialogue mouth movement, and cinematic camera cues—so you can direct AI drama scenes with more believable performances.

## The problem it addresses

AI drama videos often show fixed stares, stiff expressions, mechanical mouth movement, and camera choices with no clear story purpose. Those results are hard to improve with vague requests such as “make it more emotional” or “make it cinematic.” The model needs concrete direction about what the character does, when they do it, and how the camera observes it.

## What this Skill does

Give a compatible AI agent a script, scene, dialogue, or story outline. The Skill helps the agent:

- Identify scene beats, character intentions, and emotional changes while separating script facts from directorial inferences.
- Translate emotions into visible behavior: gaze, brows, lips, breathing, posture, hand movement, pauses, and release.
- Give dialogue shots natural mouth movement cues that follow the provided words or audio, with relaxed pauses between lines.
- Select a suitable framing, one primary camera move, focal-length reference, focus target, depth of field, and lighting direction for each shot.
- Check character, costume, prop, screen direction, lighting, and camera-axis continuity across shots.
- Assemble the decisions into prompts you can review and copy into a video-generation tool.

The Skill does not generate, edit, or export video. Video models may interpret prompts differently, so review the results and adjust them for your chosen tool.

## Who it is for

This Skill is for AI drama creators who already have a script or scene idea and want clearer performance direction, more natural dialogue shots, and more purposeful cinematic coverage. It is also useful when you know what the story should convey but are unsure how to describe the actor’s expression, timing, and camera behavior.

You will need an AI agent that can read Agent Skills. To generate a video, you will also need a video-generation tool of your choice; it is not included in this repository.

## What you get

The agent returns editable text in the conversation, usually including:

- Scene beats, character intentions, emotion labels, and intensity.
- Per-shot expressions, gaze, breathing, posture, gestures, and timing.
- Framing, camera movement, focal-length references, focus, and background sharpness.
- Natural dialogue-mouth cues and copy-ready video prompts.
- Continuity notes for characters, wardrobe, props, light, position, and movement direction.

## Install and try it

### Requirements

- An AI agent that supports Agent Skills. Installation and invocation can vary by agent.
- Node.js 22.20 or later and an internet connection when using the Vercel Skills CLI.
- A separate video-generation tool if you want to turn the prompts into video.

### Ask your AI agent to install it

You do not have to open PowerShell yourself. Copy this request into the Codex or other AI agent you are currently using:

```text
Please install this Agent Skill into the global Skills location for the AI agent currently running this conversation.

GitHub repository: yangjing6213-dev/ai-drama-quality-leap
Skill name: ai-drama-quality-leap

First check that this agent supports Agent Skills and find the official installation method and agent identifier for this operating system. If this is Codex and Node.js 22.20 or later is available, use the Vercel Skills CLI command:
npx --yes skills add yangjing6213-dev/ai-drama-quality-leap --skill ai-drama-quality-leap --global --agent codex --yes
Set DO_NOT_TRACK=1 using the syntax supported by the current shell.
For another agent, use an agent identifier officially supported by the installer and install to that agent's global Skills location. Do not assume Codex paths or identifiers apply to other tools.

Do not delete or overwrite other Skills, change unrelated settings, or ask me for passwords or access tokens. After installation, verify that the current agent can read the Skill's SKILL.md and tell me where it was installed and how to invoke it in a new conversation. If installation is unsupported or fails, stop and explain the missing requirement instead of trying unrelated installation methods.
```

This is an instruction for an AI agent, not a terminal command. The Vercel Skills CLI supports Codex and many other agents; the exact agent name and activation method depend on the tool. See the [official Skills CLI documentation](https://github.com/vercel-labs/skills) for supported agents and options.

### Install directly into Codex

On Windows PowerShell, with Node.js 22.20 or later installed, run:

```powershell
$env:DO_NOT_TRACK='1'; npx --yes skills add yangjing6213-dev/ai-drama-quality-leap --skill ai-drama-quality-leap --global --agent codex --yes
```

On macOS or Linux, run:

```sh
DO_NOT_TRACK=1 npx --yes skills add yangjing6213-dev/ai-drama-quality-leap --skill ai-drama-quality-leap --global --agent codex --yes
```

These commands install the Skill for the current user. The `DO_NOT_TRACK=1` setting asks the installer to disable its anonymous usage telemetry and applies only to that command.

### Use it

Start a new Codex conversation and enter:

```text
$ai-drama-quality-leap
```

Then paste your script or scene. Include any details you already know, such as character relationships, setting, dialogue, actions, wardrobe, props, desired duration, aspect ratio, and video tool. You do not need to fill in every item.

You can also copy this request and replace the bracketed section:

```text
$ai-drama-quality-leap

Turn the following drama scene into shot-by-shot acting direction and prompts for an AI video tool.
Preserve plot facts and dialogue. Label uncertain subtext as directorial inference. Describe visible acting, emotional progression, natural dialogue mouth movement, camera framing and movement, focus, depth of field, and continuity. End with copy-ready prompts and list any assumptions I should confirm.

Script or scene:
[Paste your scene, dialogue, and actions here]
```

For other agents, use their documented method to activate an installed Skill. The full usage guide is currently in [Chinese](USAGE.md).

## A simple workflow

```text
Script → scene beats and emotion → acting and camera direction → complete prompts → your review → video tool
```

The agent organizes the prompts. You review its directorial interpretations and use the video tool to generate and refine the final footage.

## Repository files

```text
ai-drama-quality-leap/
├── SKILL.md       # Main Skill instructions, workflow, examples, and prompt library
├── USAGE.md       # Chinese installation and beginner usage guide
├── README.md      # Chinese project overview
├── README.en.md   # English project overview
├── SOURCES.md     # Reference sources and scope notes
└── LICENSE        # MIT License
```

This repository contains Markdown documentation, not video files, application code, or a video-generation service.

## Notes and limitations

- **The character still looks stiff:** Add the actions and intentions before and after the line, then make the main visible performance change explicit for each shot. A video model may not follow every cue.
- **Mouth movement does not match dialogue:** The Skill can describe natural mouth cues, but cannot guarantee synchronization. Supplying the actual audio to a video tool that supports audio input can help.
- **Lens or aperture values have little effect:** Treat them as visual references. Also describe the subject size, focus target, and how much of the background should remain recognizable.
- **An emotion reading feels wrong:** Emotional subtext may be an inference. Keep the script facts, then edit or remove interpretations that do not fit the story.
- **Privacy and cost:** Check the data settings of your AI service before pasting unpublished scripts. AI and video-service fees depend on the tools you choose.
- **Sources and license:** The project’s rewritten examples and original files are covered by the [MIT License](LICENSE). That license does not grant rights to tutorial videos, third-party trademarks, or other external materials. See [SOURCES.md](SOURCES.md).

## Version status

There is no separate version number or GitHub release yet. Use the current `SKILL.md` in this repository as the source of truth. Performance and prompt behavior have not been verified against every video-generation model.

## Author

**Enhe (恩禾) | Product Designer · Solo Founder · AI Builder**

Building a one-person company with AI.

- GitHub: [yangjing6213-dev](https://github.com/yangjing6213-dev)
- X: [Amenenhe_ai](https://x.com/Amenenhe_ai)
- Website: [Enhe ENHE AI](https://www.enhe-tech.com.cn/)

This Skill turns “how should the character act, and how should the camera film it?” into directions an AI agent can work with. Learn more about my AI creation and work practice at [Enhe ENHE AI](https://www.enhe-tech.com.cn/).
