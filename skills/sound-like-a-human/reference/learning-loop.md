# The learning loop (how the voice file gets better)

Every edit the writer makes to a draft is a rule the system missed. Capture it. Rules are never deleted for being old: a rule that has not fired in a while may still be the one that keeps a mistake away.

## After each edit

1. When the writer edits or rewrites your draft, compare their version with yours.
2. Log each change in `voice/LEARNING-LOG.md`, newest first: the date, your phrase, their phrase, and the candidate rule ("they changed X to Y").
3. When the same kind of change shows up twice, fold it into the "Personal habits" section of `voice/voice-core.md`, newest first, with the date, and mark the log entry FOLDED. If it contradicts a line above it in the file, delete that line so the two never both apply. File it under the kind of mistake it is: five fixes of the same shape are one rule, not five.
4. When the writer says a draft "sounds like AI" without editing it, ask which line, then log that line the same way.

## After each use: count what got caught

5. After the checklist, add one tally in `voice/rule-hits.md` for every rule that caught something in this draft, and one for every rule behind a change the writer made.

## Keep the top 10 current

6. Every 10 uses, or once a week, whichever comes first, re-rank `voice/top-10.md`: the 10 rules with the most tallies, most recent tallies counting more. This page is read first on every draft, in place of the default order in `hot-filter.md`. Rules that drop out of the top 10 stay in the voice file and the ban layer; only their place in the quick check changes.

## Keeping the evidence honest

7. Pieces published through this pipeline count as edited, not as the writer's own unassisted writing. Only new dictation, chat prompts they typed, and text they confirm they wrote by hand join the gold set.
8. Every few months, re-run Step 2 of `setup.md` on the new gold writing. When a fresh count contradicts an old rule, keep both numbers with their dates.
