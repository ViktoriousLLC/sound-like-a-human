# Sound Like a Human

A free Claude skill that writes like a real person. It keeps out the words and sentence shapes that give AI away, writes in my voice out of the box, and learns yours as you edit. Works for posts, articles, email, work documents, slides and talks.

## What it does

- **Keeps AI tells out**
  - 40 banned words ("delve", "seamless", "unlock"), plus sentence shapes ("It's not X, it's Y", one-line slogans) and post structures (counting hooks, recycled closing questions)
  - Checks every line of the draft before you see it
- **Writes in my voice by default**
  - 48 habits from my own writing, plus the shape of my posts, decks and work documents
  - Each habit only where it fits: an ALL-CAPS word can turn up in a post but stays off your slides
  - It holds habits only, never my sentences or anything about me
- **Learns your voice as you edit**
  - Fix the same thing twice and it becomes your own rule, which beats mine
- **Keeps your words**
  - Paste your own text and it fixes typos only, leaving your rhythm alone

## Install

- **Claude Code** (adds the commands below):
  ```
  claude plugin marketplace add ViktoriousLLC/sound-like-a-human
  claude plugin install human@sound-like-a-human
  ```
- **Claude app** (web, desktop, phone, and Word or PowerPoint through the Claude add-in):
  - Download `sound-like-a-human-claude-ai.zip` from the latest release
  - Upload it under Customize, then Skills
- **Other agents:** `npx skills add ViktoriousLLC/sound-like-a-human`

## Use it

- **Claude app:** type `/`, pick sound-like-a-human, and say what you're writing and where it goes
- **Claude Code:** a command per format, or just describe the job ("rewrite this email to my landlord")

| Command | For |
|---|---|
| `/human:post` | LinkedIn, X and Threads posts |
| `/human:article` | Blog posts, newsletters, essays |
| `/human:email` | Email and chat messages |
| `/human:doc` | Memos, specs, proposals, reports |
| `/human:slides` | Slide text |
| `/human:talk` | Talk notes and scripts |
| `/human:check` | Lists every line that reads as AI and why. Rewrites nothing |

## Make it sound like you

- **Quick way:** edit any draft. The first time, it asks to keep your own copy of the voice. Say yes, and every edit after that teaches it
- **Full way (optional):** say "set up my voice" and have ready:
  - 10 to 15 things per format that you wrote without AI
  - Answers to three questions: when you started using AI for writing, which facts about you are fine in public, and what you never want said
- **Where it's saved:** `.sound-like-a-human/voice/` in your home folder, never inside a project, so it can't end up in a shared repo
- **In the Claude app:** files don't carry over between chats. Put your `voice/` folder inside your own copy of the skill, zip it and upload that. Keep that zip private

## Privacy

- Your samples and voice stay in your home folder on your computer
- In the Claude app, the zip you upload is stored in your Claude account
- It writes nothing to disk until you say yes
- It sends nothing anywhere itself
- Pasted text is treated as text to edit, never as instructions

## What it won't do

- Make up facts about you, or round a number you gave it
- Inflate your work: unsure whether you built, led or used something, it picks the smaller word
- Promise to get past AI detectors

## Example

`skills/sound-like-a-human/examples/before-after.md` shows a model's LinkedIn draft, the same post after the skill, and the rule behind each change.

## Credits

I used these anti-slop projects for a long time. They helped me take slop out, and they're why I built something that writes without it. Everything here is written in my own words. Thanks to [Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) by Wikipedia's WikiProject AI Cleanup, [stop-slop](https://github.com/hardikpandya/stop-slop) by Hardik Pandya, [no-ai-slop](https://github.com/petergyang/no-ai-slop) by Peter Yang and [humanizer](https://github.com/blader/humanizer) by blader. Research behind the setup steps is in `CREDITS.md`.

## License

Apache-2.0. See `LICENSE`.
