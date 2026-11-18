---
name: analyse
description: Full analysis of one YouTube video saved as its own Canva doc (stats, hook, structure, pacing, editing, packaging, what to take), with the doc's link put in that video's row of the ideas table. Use when the creator says "analyse this", "analyze this video", "break this down" on a video link (for a chat-only breakdown with no doc, use `video-breakdown`), or asks to analyse a row that's already in the ideas table. Works with the `research` skill, which builds the table.
---

# Analyse: one video → one Canva doc, linked from the ideas table

## 1. Make sure the video has a row
- Find the ideas doc in `brand/ideas_doc.md` (see the `research` skill; if there is none, create it the way `research` does).
- If the video isn't in the table yet, run the `research` steps for it first (row + thumbnail).

## 2. Watch it, don't only read it
- `python tools/yt.py watch <url>`: frames every 2 s, contact sheets and transcript in `research/<id>/`. **Read every contact sheet in order** and line it up with the transcript.
- `python tools/yt.py video <url>` and `python tools/yt.py channel <channel> --days 120` for stats and the outlier score. *(key)*
- `python tools/yt.py comments <url> --max 60` for what viewers felt and quoted. *(key)*
- Sound: Claude can't hear by default. Infer it from transcript tags like [music] and say it's inferred. With earshot installed (see README), run its `timeline` on the video.

## 3. The analysis doc
Create a Canva doc named **"Analysis: <video title>"** with these sections:
1. **Stats**: channel (subs), views, outlier ×, VPH, length, comments, publish date, link.
2. **Thumbnail and title**: what they promise, what makes them clickable.
3. **Hook (first 30 s)**: what's said and what's on screen, moment by moment.
4. **Structure**: the parts with timestamps, the promise held for the end, rehooks.
5. **Editing**: layout, how often the picture changes, text style, b-roll, graphics, sound (inferred or checked).
6. **Why it worked**: 3-5 points, each with a timestamp as proof.
7. **What to take, what to skip**: checked against `brand/about_me/` (the creator's goals, audience and style).
8. **Video ideas**: 1-3 ideas for the creator inspired by it.

Then put the doc's link in the **Analysis** column of that video's row and reply with both links (analysis doc + ideas doc).

## 4. What stays local
Frames, contact sheets, the downloaded video and the full transcript stay in `research/<id>/`. Don't upload them to Canva. Short quotes only (under 15 words), and only when needed.

## Rules
- Never invent numbers or facts; say what's missing (for example no API key).
- Ideas and structure can be borrowed. Wording and clips can't.
- Videos are downloaded only for private analysis.
