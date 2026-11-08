---
title: "Three Ways to Run Claude"
tags: [ai, tech]
categories: Useful
---

Lately I've been having way too much fun getting multiple Claude agents to work together. Along the way I figured out there are three pretty different ways to run Claude, and picking the wrong one makes orchestration a lot harder than it needs to be.

The first is the live session, which is what most people picture. You open Claude Code, type what you want, and watch it work. It asks before doing anything risky, and you can jump in and redirect it whenever it heads the wrong way. That makes it the best way to work on something you haven't figured out yet. The catch is that it needs you, and if you walk away, it waits.

So what do you do when you want Claude to run without you? That's what `claude -p` is for. The "p" stands for print. You hand it a prompt, it does the job, prints the result, and exits. Because it's just a command, you can kick it off from a script, a scheduled job, or even another agent. It still loads your skills, MCPs, and project instructions, so it knows everything your live sessions know. The thing to watch is permissions. There's nobody around to click "allow," so you have to decide up front what it's allowed to do, or it simply can't do it.

Then there's the Agent SDK, which is the same engine packaged as a library for Python or TypeScript. Instead of shelling out to Claude, your own program runs the loop. You see every step as it happens, you can hand it your own tools, and you decide in code whether each action is allowed. It's the most control, and also the most work.

Here's how I think about it now. Live sessions are for steering. `claude -p` is for jobs I can describe in one prompt and walk away from. The SDK is for when the orchestrator itself needs to be a REAL program.

I'm still learning this stuff, so ask me again in a month. My answer will probably have changed.
