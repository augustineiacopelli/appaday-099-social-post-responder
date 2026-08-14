# AppADay 099 - Social Post Responder

**Paste the feed. Keep the three posts worth answering.**

Live: https://augustineiacopelli.github.io/appaday-099-social-post-responder/

Part of [AppADay](https://augustineiacopelli.github.io/appaday/), one complete web app shipped every day.

## What it does

Drop in a batch of posts you scrolled past today. Claude reads each one and decides, honestly, whether you have anything real to add. Posts come back sorted into three piles: worth a reply, only if you know them, and skip. For the ones that survive triage you get the exact line in the post worth answering, marked in place with a highlighter, a one-line read on why it matters, the angle only you can bring, and a short reply drafted in your voice.

The whole thing is built around a fifteen minute daily outreach habit rather than around volume. Most posts in a normal feed deserve to be skipped, and the app is prompted to say so instead of manufacturing something clever for all of them.

## How it works

Paste posts into the box and tell the app how they are separated: a blank line between them, a `---` rule, or one per line. The detected count updates as you type so you can see the split is right before spending a call. Batches are read four posts at a time with a progress bar, capped at twenty per run.

Every draft lands in an editable box with a live character count against your chosen reply length and a cliche scanner underneath. The scanner flags the phrases that make a reply sound like everyone else's, along with hashtags, em dashes, and emoji, and it keeps checking as you edit. If a draft is not quite right, pick a register from the dropdown, warmer, more direct, more curious, shorter, or a polite disagreement, and rewrite just that one.

Copy the reply, mark it sent, and the footer counts your last seven days. Everything stays in the browser: the batch, your edits, what you have sent, and the running log all survive a reload.

## Care with sensitive posts

A layoff, an illness, a death, or a public failure is not a networking opportunity. The model is instructed to flag those posts, keep any reply short and plain, and mark them skip outright when you do not appear to know the poster. Flagged posts render a "handle with care" banner above the draft.

## Setup

Open the gear in the header and add your Anthropic API key. It is stored in this browser's local storage and never leaves the machine except in the request to the API. The same panel holds your voice profile: your name, what you do, what you want to be known for, the things you never say, and how long replies should run. Those notes go into every request, which is what keeps the drafts from sounding like a brand account.

Requests go directly from the browser to `api.anthropic.com` using the `anthropic-dangerous-direct-browser-access` header, on model `claude-sonnet-5`.

## Built with

One file of vanilla HTML, CSS, and JavaScript. No frameworks, no build step, no dependencies beyond Google Fonts (Familjen Grotesk, Newsreader, DM Mono). Works from a 375px phone up to a wide desktop, respects reduced motion, and validated with 201 jsdom behavioral tests covering batch splitting, response parsing, verdict handling, the cliche scanner, the highlighter, error paths, rewrite, and session restore.

---

*Ship something every day. It compounds.*
