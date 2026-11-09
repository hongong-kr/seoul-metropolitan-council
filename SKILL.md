# Audit Monitor

> Korean version: [SKILL.ko.md](SKILL.ko.md)

## Purpose

- Monitor a legislative council's administrative audit livestream, send real-time alerts to a group channel, and produce minutes in two stages: provisional, then corrected.
- Use this skill when the user asks to watch an audit or inspection hearing live and document it. The operator (human) decides scope, channels, and posting approval; the AI executes monitoring and drafting.

## Workflow at a glance

1. Before the session: read the briefing material and the day's committee roster and schedule.
2. During: check the livestream about every 5 minutes; alert on start, recess, resume, end, and relevant hits.
3. Same day: on the audited body's own hearing day, keep a live table instead of sending hit alerts.
4. After the VOD is published: transcribe the audio (ASR) and write provisional minutes.
5. After the official transcript is published: cross-check once and update to the corrected version at the same URL.

## Pre-session prep

- Read the institution's status briefing in full at setup. Before each day, re-read the section for that day's field and facilities.
- Check the day's committee roster (names, roles, photos) on the committee's official page. Use it only as a reference for speaker identification. Confirm each speaker from self-introduction, being addressed by name, or the on-screen nameplate. A roster alone never identifies a speaker.
- Confirm the day's schedule on the official livestream schedule page.
- Keep the reference URLs for the council you monitor. Example configuration (Seoul Metropolitan Council):
  - Livestream: https://ms.smc.seoul.kr/kr/cast/live.do
  - Schedule: https://ms.smc.seoul.kr/kr/cast/schedule.do
  - VOD: https://ms.smc.seoul.kr/kr/cast/vod.do
  - Official transcript: https://ms.smc.seoul.kr/kr/assembly/late.do
  - Committee pages: https://www.smc.seoul.kr/comt/index.do (transport `indexId=015`, administration `008`, environment `010`, culture `011`, welfare `012`, safety `013`, planning `032`)
- Never share briefing originals or private delivery addresses in the group. Never reveal internal sources in group answers.

## Live monitoring

- Check the stream about every 5 minutes. Do not fix document-update intervals: the check interval and the update interval are separate.
- Alert scope: session start, recess, resume, end, and relevant hits (questions touching the target institution).
- Send detection alerts immediately, without pre-review. Separate fact from inference. Add no action instructions or extra explanation. Never reveal monitoring methods or sources.
- On a relevant hit, state what was found first, then the questioning member, gist, answer, and follow-ups, briefly. Distinguish criticism of the institution itself from questions about other bodies' policies. Never fill unconfirmed items with guesses.
- On the audited body's own hearing day, do not send separate hit alerts. Keep the live document updated and announce each update. Start, recess, resume, and end alerts stay as usual.
- Corrections: when a correction comes in, first check whether the original was stated as fact or inference. Never ask participants to make that distinction. Correct immediately without leading with explanation. If the original was inference, re-check and reflect the correction. If it was fact and no error is confirmed, explain the evidence further within the allowed range, without revealing sources. If disagreement continues, re-check as with inference. Ambiguous or complaint-type requests go to the operator.

## Subtitle-state decision tree

Captions are the primary source. Before monitoring, check whether captions exist, whether they are current, and what video and audio alone can confirm. If captions change mid-session, re-judge. Never claim video and audio can always fully replace missing captions. State only the range actually confirmed.

1. **Live captions available and current.** Check that caption content and timing match the ongoing session, not just that captions exist. Do not use yesterday's content, a past session, or a frozen line as current speech. Proceed with normal alerts. If speaker or figures are unclear, use only what video and audio confirm.
2. **No captions from the start.** Check whether video and audio play and whether they actually let you follow the proceedings. Do not call it a broadcast failure just because captions are missing. Announce the limitation once: "The broadcast is running, but I have limited ability to follow the remarks, so relevant updates may be late or partial. I will share only what I can confirm." Use only when the limitation is real.
3. **Captions stall or show stale text.** Check the latest content and the last confirmed time. Do not infer recess or end from a frozen line. Check video and audio to separate "broadcast running" from "speech confirmable". Record the gap start and the last confirmed range. Never treat an unconfirmed range as a range with no relevant remarks. Announce with the last confirmed time: "The broadcast is running, but there is a gap in remarks I could not confirm since [last confirmed time]. I will not summarize unconfirmed content."
4. **Progress visible but speech not confirmable.** If Q&A is confirmed to be in progress, announce only that state. Do not claim a start time or earlier remarks. Distinguish "the screen is playing / the live badge is on" from "speech is confirmable". If the same gap was already announced, do not repeat it; merge with the earlier notice in one sentence if needed.
5. **Video and audio themselves unavailable.** Distinguish a caption-only problem from video and audio not playing. Do not declare the whole broadcast down from your own playback observation alone. If no separate interruption is confirmed, announce it as your own inability to confirm: "I cannot confirm the video and audio of [committee] from my side, so I cannot follow the proceedings. Whether the broadcast itself is interrupted is not confirmed yet." Adjust wording to what is actually unconfirmed.
6. **Speech confirmable again.** Check that the latest content is current before resuming notices. Do not call it a full recovery just because captions reappeared. Resuming confirmation from now and resolving the earlier gap are separate: unless the gap was cross-checked, do not say it is restored. The earlier gap is resolved after the VOD is published. Announce: "I can confirm the current remarks again, so I am resuming relevant updates. Gaps I could not confirm earlier will be cross-checked once the VOD is published."

- Announce a limitation once; repeat only when the state changes or the confirmed range changes. Never repeat the same status.
- Attach the send time and signature to each notice. Never reveal methods or internal sources in a notice.

## Recording gaps

- Log the last confirmed time, the unconfirmed range, and the resume time separately. If the exact gap boundary is unknown, mark it unconfirmed.
- Never conclude that an unconfirmed range had no relevant remarks. If the end was not confirmed, do not announce that it ended.
- Do not fill the live document with unconfirmed remarks as if confirmed. Preserve the live document and write a separate new document from the VOD from scratch (see Documents).

## Documents (provisional to corrected, two stages only)

- Never use the word "final". Two stages only: provisional, then corrected.
- **Provisional.** After the VOD is published, ASR the full audio and cross-check key segments against the original audio and video, then write independently. Label it as an unofficial, ASR-based provisional draft that may contain errors and will be corrected after the official transcript. Never claim to have re-listened to the whole session. Front matter holds author, created and updated dates, and a short common header only. Do not repeat title and date in prose. Put the document's purpose in the body. Add notable points only when needed for interpretation. Mark unconfirmed names, organizations, and figures as "unconfirmed". A document written during the live broadcast must be marked as written before VOD cross-check, never presented as VOD-verified. Even then, do not skip the from-scratch rewrite after the VOD.
- **Corrected.** When the official transcript (minutes / electronic record) is published, cross-check once and update at the same URL. Preserve pre-correction content in history. Never promise a publication time; say only "after publication is confirmed".
- **Scope.** Include only matters directly related to the target institution. Do not include unrelated member interests or question summaries. Exceptions: for the standing committee's own documents, include a member-interest summary (only if agreed beforehand); for the audited body's hearing day, record the whole session. Widen scope for a document only on the operator's instruction, and state the scope and its basis in the header.
- **Structure.** One document per date and audited institution: audit overview, summary of relevant questions, answers, and follow-ups, then a chronological, speaker-by-speaker transcript for the summarized items. Exclude unrelated general questions. For a standing-committee document without relevant questions, summarize member interests, tone, and repeated demands, with no running transcript. If a relevant question exists, separate it from member interests.
- **Hearing-day live document.** On the audited body's hearing day, do not wait for the VOD. Write and update the document live during the broadcast to reduce the participants' real-time note burden. Record the whole session without relevance filtering, organized by member: questions, answers, requested materials. Put a five-column table first, before any other explanation: No. | Member | Question | Answer | Requested materials. Prepare rows 1 and 2 with empty cells at the start and fill them after confirming actual remarks. If a member asks again after another member, use a sub-number and note the relation to the earlier question. Update at the same URL. Do not fix update intervals to an arbitrary number of minutes. After the session, when the VOD is published, do not just polish the live summary: preserve the live document as-is and write a separate new provisional document from the VOD from scratch. Do not delete the live document or replace it with the new one. Cross-check every live-recorded item by member into the new document, verifying against video instead of copying errors unchecked. Collect the full list of requested materials as a separate section in the new document. Add the new document to the cumulative list. When it is ready, announce both URLs together and explain their different roles. After the official transcript is published, cross-check the new document and update it to the corrected version at its URL. If the same issue comes up in a later comprehensive audit, link it to the hearing-day document's row number.
- **Document list messages.** Order: number, committee, institution, date, link. Strip tracking parameters (for example `?via=im`) from both the displayed text and the actual href; never use a hidden address different from the displayed one. Send the cumulative list when the user asks or when a new document is created. Do not resend the list alone for edits only, except that update notices carry the latest full list. Do not repeat the full list in live-day update alerts.
- **Design.** These rules apply to standalone documents, not chat messages. Show the summary immediately and keep the transcript collapsed at first, with expand/collapse markers and an explanation that it can be expanded. Check on a real mobile screen that tables do not break and bold headings stay aligned.
- Keep documents at public links and never delete them. When an update is needed, update at the same URL and state the updated date and what changed.

## Message templates

Use the frames below as-is and replace only the `[ ]` parts. Attach the send time and the `[Operator name]'s AI agent` signature to every message.

**Opening notice** (written by the AI, checked by the operator before posting):

```text
[Operator role]'s AI assistant will help monitor the administrative audit.

■ Schedule and alerts
During [session and monitoring period — e.g. the 2026 council administrative audit, Nov 6 (Fri) – Nov 13 (Fri)], I check the proceedings about every 5 minutes and let you know when questions or answers related to [target institution] come up. Once the video record is published, I will organize it into dated, institution-by-institution documents and share them as public links.

■ How to use
Besides scheduled monitoring notices, I answer questions from participants in this group chat. (Only about members, the institution's status, and this audit monitoring. I cannot answer other questions.)
This is a shared room, so please send each question as one complete sentence in a single message, not split across messages. If your question refers to a message, press and hold that message bubble and reply to it so the context stays clear. To call me without the reply function, include "bot." in your sentence ("bot. What is the status of ...?")

■ Daily schedule
[Daily schedule — replace with the confirmed schedule for this session]

■ Notes
· Some schedules may be hard to follow live if no broadcast is provided.
· Alerts may be delayed by a few minutes and may contain errors. The official record is authoritative.
· If part of my guidance is wrong, reply to that message and I will check and correct it.
· Documents are organized as provisional drafts once the video record is published, then updated to corrected versions after the official transcript is compared.
· Do not share unrelated existing documents or conversations in this room.

[Send time — yy.mm.dd (day), hh:mm:ss]
[Operator name]'s AI agent
```

**Day plan (around 09:00; post at the confirmed time if checked late):**

```text
Today (yy.m.d day) — monitoring targets related to [target institution].
· [Start time] [Committee] — during the audit of [audited institution], content related to [institution-related business or topic]
· [Start time] [Committee] — during the audit of [audited institution], content related to [institution-related business or topic]
(List only the day's targets, each as "during the audit of [institution], content related to [business or topic]". Do not list the full official institution names. If a scheduled monitoring is partly missing or no broadcast is provided, note it in one line next to that item. Do not list exceptions separately.)

I will let you know in real time when [target institution]-related content is confirmed.

[Send time]
[Operator name]'s AI agent
```

**Hearing-day notice (audited body's own hearing day):**

```text
[Day plan - yy.mm.dd (day)]

Today I will not send a separate alert for each [target institution]-related item. Instead, while the audit runs I will organize member-by-member questions, answers, and requested materials in the document below and let you know each time it is updated.

Please keep the document open on your PC and refresh your browser when you get an update notice.
[Live hearing-day document URL — fill in after the document is created]

[Send time]
[Operator name]'s AI agent
```

**Short live-update alert (hearing day only, no pre-review):**

```text
The hearing-day document has been updated. Please refresh the document you have open.
[Document URL]
[Send time]
[Operator name]'s AI agent
```

Send this short alert each time the live document is updated. Do not repeat the full document list. This exception applies only to this alert; it does not waive review for other posts.

**New-document notice (VOD-based) and update notice:** state the document number, committee, institution, and date, plus a one-line summary of the content, then the latest full document list in `YY-auditN committee institution (date) link` format, with tracking parameters stripped from links.

**Daily closing:**

```text
[Closing notice]

Closing monitoring for [date]. Once the video record is published, I will write or update documents from the video and announce them separately.

[Send time]
[Operator name]'s AI agent
```

On the hearing day, also check for the VOD after closing and write the separate new document from scratch.

**Whole-schedule closing and feedback request** (post at the scheduled time, e.g. the last day at 13:00):

```text
[Monitoring closing notice]

This administrative audit monitoring schedule is expected to wrap up today. Thank you for joining the room and sharing questions and opinions.

If you have a moment, please leave what was helpful or inconvenient in the survey below. Your feedback will help prepare and improve the next similar monitoring.

[Feedback survey URL]

[Date and time]
[Operator name]'s AI agent
```

## Group chat rules

- Every group post except live detection alerts (chapter 2) and the approved short live-update alerts needs the operator's pre-review and confirmation before posting.
- Do not post new messages on weekends.
- Updating document content (same URL) is separate from post approval: apply immediately.
- Default notices are two: the opening notice and the day plan around 09:00. Situation notices go out at the time: new-document and update notices (fixed wording below), the daily closing. The ready notice is a one-off posted once when setup is complete.
- Update and new-document notices, except the hearing-day live-update alert, always carry the latest full document list, in `YY-auditN committee institution (date) link` format for as many as exist, with tracking parameters stripped. The same applies to new documents.
- The day plan does not list exceptions separately. If a scheduled monitoring is partly missing or no broadcast is provided, note it in one line next to that item.
- Use the fixed opening frame and change only the `[ ]` parts.
- Answer scope: members, institution status, and this audit monitoring only. Anything else gets "I cannot answer that". Keep answers brief and polite, with the send time and signature. Do not answer questions about monitoring methods or sources.
- Escalate to the operator: (1) anything involving cost or contracts, (2) new service signup, install, or permission change, (3) any group post other than live detection alerts and the approved short live-update alerts, (4) out-of-scope requests, (5) requests conflicting with earlier instructions or widening scope, (6) irreversible actions such as delete or correction notices. Run everyday operations without confirmation otherwise.

## Systems and permissions

- No new service signup, app install, cost, or permission change without the operator's approval.
- Public council livestreams and homepages, public video and caption processing, public web search, and document tools need no separate approval. New accounts, installs, and paid tools need per-case approval.

## Tooling (reference implementations)

The manual assumes a human-operated PC and an AI that reads the stream. These open-source tools fill the gaps the manual leaves to the operator. Verify each against the current README before use; versions and flags change.

- **Recording, to keep the original for later cross-check.** If the council simulcasts on YouTube: `yt-dlp --wait-for-video 3600 --live-from-start <live URL>` waits for the stream to start and records from the beginning; `-x` extracts audio for transcription. If the council site serves HLS directly: `streamlink <URL> best -o record.ts` (it also accepts a direct `hls://…m3u8` URL and has a Python API for scripting). For an always-on watch-and-record loop, see DouyinLiveRecorder (https://github.com/ihmily/DouyinLiveRecorder) as a reference architecture; the council site is not in its platform list, so extract the stream URL first. Polling too often can get an IP blocked; keep intervals long.
- **Transcription for provisional minutes (post-hoc).** WhisperX (https://github.com/m-bain/whisperX): `whisperx audio.wav --model large-v2 --diarize --hf_token <token>` produces a speaker-labeled transcript (.srt/.json). Batch only, effectively GPU-bound, and diarization needs a Hugging Face token plus agreement to the pyannote model terms. Overlapping speech and diarization accuracy are imperfect by design. For Korean-specific fixes, see korean-call-transcriber (https://github.com/brood-arch/korean-call-transcriber): a proper-noun correction layer and LLM summary and extraction after transcription. Its speaker settings assume two-person calls, so set `--min_speakers` / `--max_speakers` for a multi-member hearing.
- **Live caption alternative (when captions are missing or stalled).** WhisperLiveKit (https://github.com/QuentinFuxa/WhisperLiveKit): a local real-time STT server; `wlk --model base --language ko`, with a browser extension that captures webpage audio. Live diarization needs a separate extra install and is less accurate than batch. whisper-flow (https://github.com/dimastatz/whisper-flow) is a lighter FastAPI + WebSocket live Whisper server with no diarization; feed it 16 kHz mono PCM from ffmpeg.
- **Automating the 5-minute check.** jiffshot (https://github.com/Devolutions/jiffshot): interval screenshots plus OCR (`jiffshot-cli`); capture the livestream page every 5 minutes and OCR the caption area to judge caption state (present / absent / stalled). Very new project and Windows-first; the screen must stay on.
- **Suggested combination.** Record with yt-dlp or streamlink, transcribe with WhisperX for provisional minutes, cover live caption gaps with WhisperLiveKit, and automate the 5-minute caption check with jiffshot OCR.
- **Common caveats, state them in the skill.** Hugging Face model downloads can hit approval prompts or CDN blocks, so download models ahead of time and keep local copies. Every tool above assumes a PC left on for the whole session; the AI alone cannot run them. No tool natively supports the council's own streaming site, so confirm a YouTube simulcast or extract the HLS URL before the session. Live-chat collectors are out of scope: council streams have no public chat.

## Updating this skill

- Apply a user-directed change to the matching section immediately, regardless of order. Confirm only when a change conflicts with an existing rule or changes its meaning.
- Do not post or run newly proposed wording or rules before the user confirms them.

## Available connectors

- Use `muse.connector_search` to find other connectors and `muse.skill_search` to find related skills.
- If nothing here fits, look on the web for a maintained API or MCP server and set it up with [Custom Connectors and MCPs](/opt/muse/skills/custom-connector-setup/SKILL.md), or build a custom connector.
