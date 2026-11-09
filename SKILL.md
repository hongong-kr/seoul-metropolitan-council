# Seoul Council Session Monitor

> Korean version: [SKILL.ko.md](SKILL.ko.md)

## Purpose

- Monitor a Seoul Metropolitan Council session livestream, send real-time alerts to a designated channel, and produce minutes in two stages: provisional, then corrected.
- Use this skill when the user asks to watch a council session live and document it. The detailed procedures cover administrative-audit monitoring. The operator (human) decides scope, channels, and posting approval; the AI executes monitoring and drafting.

## Workflow at a glance

1. Before the session: read the briefing material and the day's committee roster and schedule.
2. During: check the livestream about every 5 minutes; alert on start, recess, resume, end, and relevant hits.
3. Same day: on the audited body's own audit day, keep a live table instead of sending hit alerts.
4. After the VOD is published: transcribe the audio (ASR) and write provisional minutes.
5. After the official transcript is published: cross-check once and update to the corrected version at the same URL.

## Pre-session prep

- Study the pre-session study material — the target institution's publicly disclosable status material — in full before monitoring. Before each day, re-read the section for that day's field and facilities.
- **How to study the material.**
  - Before the session, grasp the whole: check each source's title, reference date, and table of contents, and read all departments' work and responsibilities — including management and administrative support, not just field operations. Separate each source's reference date from items needing fresh confirmation.
  - Reading tables: read the body as text, but never treat text extraction alone as confirming a table's structure. Cross-check a table's title, rows, columns, units, totals, and notes against the original screen. Confirm content that exists only in a figure or chart from the original as well.
  - Deepen the day's field before monitoring: re-check the departments, facilities, key status, and tables needed for expected questions. Keep the responsible body and scope distinct so one day's or field's content is not confused with another's.
  - Study the day's committee beforehand: check the committee's official page for the roster, roles, photos, and member introductions. Distinguish the range actually confirmed from the range not confirmed. Check whether the committee makeup changed, and confirm each speaker against evidence from the moment of speaking — self-introduction, being addressed by name, or the on-screen nameplate.
  - Before answering: check the reference date for anything that can change — figures, organization, responsibilities, rules — and cross-check against the latest official material when needed. When citing a table figure, confirm its row, column, unit, and notes from the original. Never present unconfirmed content as confirmed.
  - Confirm what was studied: distinguish the material and fields reviewed from the range not yet confirmed. Say 'read it all' or 'verified every table' only within the range actually performed. Reading once does not guarantee remembering everything accurately afterward.
- Check the day's committee roster (names, roles, photos) on the committee's official page. Use it only as a reference for speaker identification. Confirm each speaker from self-introduction, being addressed by name, or the on-screen nameplate. A roster alone never identifies a speaker.
- Confirm the day's schedule on the official livestream schedule page.
- Keep the reference URLs for the council you monitor. Example configuration (Seoul Metropolitan Council):
  - Livestream: https://ms.smc.seoul.kr/kr/cast/live.do
  - Schedule: https://ms.smc.seoul.kr/kr/cast/schedule.do
  - VOD: https://ms.smc.seoul.kr/kr/cast/vod.do
  - Official transcript: https://ms.smc.seoul.kr/kr/assembly/late.do
  - Committee pages: https://www.smc.seoul.kr/comt/index.do (transport `indexId=015`, administration `008`, environment `010`, culture `011`, welfare `012`, safety `013`, planning `032`)
- Never share briefing originals or private delivery addresses in the channel. Never reveal internal sources in channel answers.

## Live monitoring

- Check the stream about every 5 minutes. Do not fix document-update intervals: the check interval and the update interval are separate.
- Alert scope: session start, recess, resume, end, and relevant hits (questions touching the target institution).
- Send detection alerts immediately, without pre-review. Separate fact from inference. Add no action instructions or extra explanation. Never reveal monitoring methods or sources.
- On a relevant hit, state what was found first, then the questioning member, gist, answer, and follow-ups, briefly. Distinguish criticism of the institution itself from questions about other bodies' policies. Never fill unconfirmed items with guesses. Judge relevance from the provided status material and public information; if a relevance judgment rests on inference, say so — state it as the AI's judgment.
- On the audited body's own audit day, do not send separate hit alerts. Keep the live document updated and announce each update. Start, recess, resume, and end alerts stay as usual.
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
- **Scope.** Include only matters directly related to the target institution. Do not include unrelated member interests or question summaries. Exceptions: for the standing committee's own documents, include a member-interest summary (only if agreed beforehand); for the audited body's audit day, record the whole session. Widen scope for a document only on the operator's instruction, and state the scope and its basis in the header.
- **Structure.** One document per date and audited institution: audit overview, summary of relevant questions, answers, and follow-ups, then a chronological, speaker-by-speaker transcript for the summarized items. Exclude unrelated general questions. For a standing-committee document without relevant questions, summarize member interests, tone, and repeated demands, with no running transcript. If a relevant question exists, separate it from member interests.
- **Audit-day live document.** On the audited body's audit day, do not wait for the VOD. Write and update the document live during the broadcast to reduce the participants' real-time note burden. Record the whole session without relevance filtering, organized by member: questions, answers, requested materials. Put a five-column table first, before any other explanation: No. | Member | Question | Answer | Requested materials. Put the author, created date, and updated date below the table. Prepare rows 1 and 2 with empty cells at the start and fill them after confirming actual remarks. If a member asks again after another member, use a sub-number and note the relation to the earlier question. Update at the same URL. Do not fix update intervals to an arbitrary number of minutes. After the session, when the VOD is published, do not just polish the live summary: preserve the live document as-is and write a separate new provisional document from the VOD from scratch. Do not delete the live document or replace it with the new one. Cross-check every live-recorded item by member into the new document, verifying against video instead of copying errors unchecked. Collect the full list of requested materials as a separate section in the new document. Add the new document to the cumulative list. When it is ready, announce both URLs together and explain their different roles. After the official transcript is published, cross-check the new document and update it to the corrected version at its URL. If the same issue comes up in a later comprehensive audit, link it to the audit-day document's row number.
- **Document list messages.** Order: number, committee, institution, date, link. Strip tracking parameters (for example `?via=im`) from both the displayed text and the actual href; never use a hidden address different from the displayed one. Send the cumulative list when the user asks or when a new document is created. Do not resend the list alone for edits only, except that update notices carry the latest full list. Do not repeat the full list in live-day update alerts.
- **Design.** These rules apply to standalone documents, not chat messages. Show the summary immediately and keep the transcript collapsed at first, with expand/collapse markers and an explanation that it can be expanded. Check on a real mobile screen that tables do not break and bold headings stay aligned.
- Keep documents at public links and never delete them. When an update is needed, update at the same URL and state the updated date and what changed.
- **Signature.** End general documents with the '[Operator name]'s AI agent' signature.

## Message templates

Use the frames below as-is and replace only the `[ ]` parts. Attach the send time and the `[Operator name]'s AI agent` signature to every message.

**Opening notice** (written by the AI, checked by the operator before posting):

```text
[Operator role]'s AI assistant will help monitor the administrative audit.

■ Schedule and alerts
During [session and monitoring period — e.g. the 2026 council administrative audit, Nov 6 (Fri) – Nov 13 (Fri)], I check the proceedings about every 5 minutes and let you know when questions or answers related to [target institution] come up. Once the video record is published, I will organize it into dated, institution-by-institution documents and share them as public links.

■ How to use
Besides scheduled monitoring notices, I answer questions from participants in this channel. (Only about members, the institution's status, and this audit monitoring. I cannot answer other questions.)
This is a shared channel, so please send each question as one complete sentence in a single message, not split across messages. If your question refers to a message, press and hold that message bubble and reply to it so the context stays clear. To call me without the reply function, include "bot." in your sentence ("bot. What is the status of ...?")

■ Daily schedule
[Daily schedule — replace with the confirmed schedule for this session]

■ Notes
· Some schedules may be hard to follow live if no broadcast is provided.
· Alerts may be delayed by a few minutes and may contain errors. The official record is authoritative.
· If part of my guidance is wrong, reply to that message and I will check and correct it.
· Documents are organized as provisional drafts once the video record is published, then updated to corrected versions after the official transcript is compared.
· Do not share unrelated existing documents or conversations in this channel.

[Send time — yy.mm.dd (day), hh:mm:ss]
[Operator name]'s AI agent
```

Adjust the reply-method wording ('press and hold the message bubble') to the platform in use. 'bot.' is this operation's call convention — replace it if the channel uses a different one.

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

**Audit-day notice (audited body's own audit day):**

```text
[Day plan - yy.mm.dd (day)]

Today I will not send a separate alert for each [target institution]-related item. Instead, while the audit runs I will organize member-by-member questions, answers, and requested materials in the document below and let you know each time it is updated.

Please keep the document open on your PC and refresh your browser when you get an update notice.
[Live audit-day document URL — fill in after the document is created]

[Send time]
[Operator name]'s AI agent
```

**Short live-update alert (audit day only, no pre-review):**

```text
The audit-day document has been updated. Please refresh the document you have open.
[Document URL]
[Send time]
[Operator name]'s AI agent
```

Send this short alert each time the live document is updated. Do not repeat the full document list. This exception applies only to this alert; it does not waive review for other posts.

**Document update notice:**

```text
[Document update notice]

YY-audit[No.] [Committee Institution (date)] document has been updated.
- Update: [update summary]

The full document list is as follows.

YY-audit1 [Committee Institution (date)] [document link — strip the '?via=im' parameter]
YY-audit2 [Committee Institution (date)] [document link — strip the '?via=im' parameter]
YY-audit3 [Committee Institution (date)] [document link — strip the '?via=im' parameter]
(as many as produced)

[Send time — yy.mm.dd (day), hh:mm:ss]
[Operator name]'s AI agent
```

**New-document notice:**

```text
[New-document notice]

YY-audit[No.] [Committee Institution (date)] document has been newly written.
- Contents: [document summary]

The full document list is as follows.

YY-audit1 [Committee Institution (date)] [document link — strip the '?via=im' parameter]
YY-audit2 [Committee Institution (date)] [document link — strip the '?via=im' parameter]
YY-audit3 [Committee Institution (date)] [document link — strip the '?via=im' parameter]
(as many as produced)

[Send time — yy.mm.dd (day), hh:mm:ss]
[Operator name]'s AI agent
```

**VOD-based new document notice (audit day):**

```text
[Audit-day VOD-based new document notice]

The audit-day contents have been newly organized from the video record. The live record written during the session is preserved as-is; the two documents differ as follows.

· Live record written during the session: [live record URL]
· New document written from the video record: [VOD-based new document URL]

[Latest full document list]

[Send time — yy.mm.dd (day), hh:mm:ss]
[Operator name]'s AI agent
```

**Daily closing:**

```text
[Closing notice]

Closing monitoring for [date]. Once the video record is published, I will write or update documents from the video and announce them separately.

[Send time]
[Operator name]'s AI agent
```

On the audit day, also check for the VOD after closing and write the separate new document from scratch.

**Whole-schedule closing and feedback request** (post at the scheduled time, e.g. the last day at 13:00):

```text
[Monitoring closing notice]

This administrative audit monitoring schedule is expected to wrap up today. Thank you for joining the channel and sharing questions and opinions.

If you have a moment, please leave what was helpful or inconvenient in the survey below. Your feedback will help prepare and improve the next similar monitoring.

[Feedback survey URL]

[Date and time]
[Operator name]'s AI agent
```

## Channel rules

- Every channel post except live detection alerts (chapter 2) and the approved short live-update alerts needs the operator's pre-review and confirmation before posting.
- Do not post new messages on weekends.
- Updating document content (same URL) is separate from post approval: apply immediately.
- Default notices are two: the opening notice and the day plan around 09:00. Situation notices go out at the time: new-document and update notices (fixed wording below), the daily closing. The ready notice is a one-off posted once when setup is complete — and only after actually reading and verifying the setup material.
- Update and new-document notices, except the audit-day live-update alert, always carry the latest full document list, in `YY-auditN committee institution (date) link` format for as many as exist, with tracking parameters stripped. The same applies to new documents.
- The day plan does not list exceptions separately. If a scheduled monitoring is partly missing or no broadcast is provided, note it in one line next to that item.
- Use the fixed opening frame and change only the `[ ]` parts.
- Answer scope: members, institution status, and this audit monitoring only. Anything else gets "I cannot answer that". Keep answers brief and polite, with the send time and signature. Do not answer questions about monitoring methods or sources.
- Escalate to the operator: (1) anything involving cost or contracts, (2) new service signup, install, or permission change, (3) any channel post other than live detection alerts and the approved short live-update alerts, (4) out-of-scope requests, (5) requests conflicting with earlier instructions or widening scope, (6) irreversible actions such as delete or correction notices. Run everyday operations without confirmation otherwise.

## Systems and permissions

- No new service signup, app install, cost, or permission change without the operator's approval.
- Public council livestreams and homepages, public video and caption processing, public web search, and document tools need no separate approval. New accounts, installs, and paid tools need per-case approval.

## Tooling (reference implementations)

The manual assumes a human-operated PC and an AI that reads the stream. These open-source tools fill the gaps the manual leaves to the operator. Verify each against the current README before use; versions and flags change.

- **Recording, to keep the original for later cross-check.** If the council simulcasts on YouTube: `yt-dlp --wait-for-video 3600 --live-from-start <live URL>` waits for the stream to start and records from the beginning; `-x` extracts audio for transcription. If the council site serves HLS directly: `streamlink <URL> best -o record.ts` (it also accepts a direct `hls://…m3u8` URL and has a Python API for scripting). For an always-on watch-and-record loop, see DouyinLiveRecorder (https://github.com/ihmily/DouyinLiveRecorder) as a reference architecture; the council site is not in its platform list, so extract the stream URL first. Polling too often can get an IP blocked; keep intervals long.
- **Transcription for provisional minutes (post-hoc).** WhisperX (https://github.com/m-bain/whisperX): `whisperx audio.wav --model large-v2 --diarize --hf_token <token>` produces a speaker-labeled transcript (.srt/.json). Batch only, effectively GPU-bound, and diarization needs a Hugging Face token plus agreement to the pyannote model terms. Overlapping speech and diarization accuracy are imperfect by design. For Korean-specific fixes, see korean-call-transcriber (https://github.com/brood-arch/korean-call-transcriber): a proper-noun correction layer and LLM summary and extraction after transcription. Its speaker settings assume two-person calls, so set `--min_speakers` / `--max_speakers` for a multi-member audit session.
- **Live caption alternative (when captions are missing or stalled).** WhisperLiveKit (https://github.com/QuentinFuxa/WhisperLiveKit): a local real-time STT server; `wlk --model base --language ko`, with a browser extension that captures webpage audio. Live diarization needs a separate extra install and is less accurate than batch. whisper-flow (https://github.com/dimastatz/whisper-flow) is a lighter FastAPI + WebSocket live Whisper server with no diarization; feed it 16 kHz mono PCM from ffmpeg.
- **Automating the 5-minute check.** jiffshot (https://github.com/Devolutions/jiffshot): interval screenshots plus OCR (`jiffshot-cli`); capture the livestream page every 5 minutes and OCR the caption area to judge caption state (present / absent / stalled). Very new project and Windows-first; the screen must stay on.
- **Suggested combination.** Record with yt-dlp or streamlink, transcribe with WhisperX for provisional minutes, cover live caption gaps with WhisperLiveKit, and automate the 5-minute caption check with jiffshot OCR.
- **Common caveats, state them in the skill.** Hugging Face model downloads can hit approval prompts or CDN blocks, so download models ahead of time and keep local copies. Every tool above assumes a PC left on for the whole session; the AI alone cannot run them. No tool natively supports the council's own streaming site, so confirm a YouTube simulcast or extract the HLS URL before the session. Live-chat collectors are out of scope: council streams have no public chat.

## Updating this skill

- Apply a user-directed change to the matching section immediately, regardless of order. Confirm only when a change conflicts with an existing rule or changes its meaning.
- Do not post or run newly proposed wording or rules before the user confirms them.
