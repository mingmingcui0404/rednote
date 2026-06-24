---
name: xhs-chrome-publisher
description: Generate a Xiaohongshu-style article from a user-provided direction, format it for publishing, update a local Xiaohongshu publishing workspace when available, and use the user's logged-in Chrome session/cookies to open Xiaohongshu and prepare a post. Use when the user asks to create, rewrite, format, stage, or publish Xiaohongshu content through Chrome with their existing login.
---

# Xhs Chrome Publisher

## Core Workflow

Use this workflow when the user gives a topic, direction, product angle, philosophical theme, personal story, or marketing brief and wants a Xiaohongshu post prepared or published through Chrome.

1. Clarify only if the direction is too ambiguous to write safely. Otherwise choose a concrete angle and proceed.
2. Generate a polished Xiaohongshu-style article:
   - Title: concise, curiosity-driven, not clickbait or absolute.
   - Hook: first sentence should name a felt tension, question, or benefit.
   - Body: short paragraphs, concrete examples, useful insight, and a natural ending.
   - Tags: 4-8 relevant hashtags, no unrelated traffic tags.
   - Suggested visuals: cover idea plus 2-4 supporting image ideas.
   - Engagement plan: 2-4 manual follow-up tasks or comment prompts.
3. If a local publishing workspace exists, update it:
   - Prefer existing data structures and UI patterns.
   - Put the new draft first in the content library.
   - Increment any local storage key/version if old browser data may hide the new draft.
   - Run the lightest available syntax check for edited scripts.
4. Prepare a publish-ready text block:
   - Title on the first line.
   - Hook and body separated by blank lines.
   - Hashtags at the end.
5. Use the Chrome browser skill for Xiaohongshu browser work because the task depends on the user's logged-in cookies.
6. Open Xiaohongshu in Chrome with the user's existing session. Do not inspect, export, print, store, or ask for cookies.
7. Navigate the visible UI to the creator/publish flow. Use the site's own controls rather than undocumented internal endpoints.
8. Fill the post fields when the UI clearly supports it:
   - Put the title in the title field.
   - Put the body and tags in the text/content field.
   - Upload images only when the user has provided or approved specific local files.
9. Stop before the final publish/submission action unless the user explicitly confirmed publishing this exact post in the current turn.

## Safety And Consent

- Treat final publishing as an external side effect. Confirm immediately before clicking any button that posts, publishes, submits, schedules, or otherwise makes content public.
- If the user previously said "publish", that is enough to prepare the draft and reach the final confirmation point, but still confirm before the final click unless the exact post text and action were already approved in the same turn.
- Do not automate likes, follows, comments, favorites, private messages, or other artificial engagement.
- Do not bypass Xiaohongshu rate limits, moderation, login checks, or anti-automation controls.
- Do not scrape private user data. Use only information visible and necessary for publishing the requested post.
- Do not expose authentication details. Never copy cookies, local storage tokens, request headers, QR codes, or account secrets into responses or files.

## Writing Style

Write in natural Chinese for Xiaohongshu:

- Prefer phrases such as `我发现...`, `后来我意识到...`, `真正重要的是...`, and `给你一个小练习...` when appropriate.
- Keep paragraphs short enough for mobile reading.
- Use specific emotional or practical scenarios instead of abstract slogans.
- Avoid exaggerated guarantees such as `必爆`, `一定涨粉`, `永久解决`, or medical/financial/legal certainty.
- For philosophical topics, connect concepts to daily experience, then return to the concept with sharper language.
- For commercial topics, include suitable users, unsuitable users, and a factual caveat.

## Local Workspace Update

When updating a simple static workspace similar to `index.html`, `app.js`, and `styles.css`:

- Add the new item to the beginning of `seedDrafts`.
- Include fields compatible with existing cards: `title`, `hook`, `body`, `tags`, `status`, `publishDate`, `assets`, and `engagementTasks`.
- Use `status: "已排期"` when the user wants it ready for publishing; use `草稿` when they are still iterating.
- Use today's date or the next sensible date only if the user does not provide a date.
- Check JavaScript with `node --check app.js` when available.

## Chrome Publishing Notes

- Use Chrome only after the content is ready enough to publish.
- Prefer the existing selected tab if it is already on Xiaohongshu; otherwise open a new tab.
- If login is missing, ask the user to log in manually and continue after they say it is ready.
- If the UI requires images and none are available, stop with a clear note and offer cover/image suggestions.
- If a CAPTCHA, identity check, or platform warning appears, stop and ask the user to handle it manually.
- After filling the draft, summarize what is ready and ask for final confirmation before publishing.
