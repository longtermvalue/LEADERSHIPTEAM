# 📥 Inbox — drop anything here

**The zero-thought upload path.** Don't know (or care) which folder a file belongs
in? Put it here — statements, exports, contracts, screenshots, spreadsheets, all
mixed together is fine — then ask Claude to **"file my uploads"** or run
**`/file-inbox`**.

Claude will identify each file, rename it to the dated convention, move it to the
correct `channels/<channel>/data/` folder, record it in `filing-log.md`, and offer
to run the matching analysis (statements → `/analyze-statements`, ad exports →
`/ad-review`, and so on). Anything it can't confidently identify stays here, with a
one-line question for you instead of a guess.

Ways to get files into this folder:
- **GitHub website**: open this `inbox/` folder → **Add file → Upload files** →
  drag everything in → Commit. (One folder to remember — this one.)
- **Claude Code session**: attach the file(s) in chat and say "file these" —
  Claude treats attachments exactly like inbox drops.
- **Git**: copy files in, commit, push.
- **Slack** (if connected): upload in the mapped channel and ask @Claude to file it.

Notes:
- Files are *moved out* of here when filed — an empty inbox means all caught up.
- Don't drop files containing passwords/recovery codes, and expect SINs or full
  card numbers to be flagged; GitHub also rejects files over 100 MB.
