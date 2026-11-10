# Setup: build the writer's voice file

You are building a personal voice file for one writer. Work the five steps in order, fill every [BLANK] from the writer's own writing, and attach a count or a verbatim quote to every claim. The output goes in the writer's voice folder (SKILL.md says where; by default `.sound-like-a-human/voice/` in their home folder), never into a copy of this skill that anyone else will see, and it stays private to them.

## Why style guides fail

- Verbatim examples beat descriptions. "Catch Me If You Can? Not Yet" (EMNLP 2025 Findings, https://arxiv.org/html/2509.14543v1) measured zero-shot imitation at under 7% attribution accuracy, five verbatim samples roughly doubling it, and statistical style summaries were not effective anchors. Results barely moved from 2 to 10 examples; picking samples close in topic and length beats adding more.
- Negative examples work. Contrastive in-context learning (AAAI 2024, https://arxiv.org/abs/2401.17390): good examples paired with avoid-this examples beat standard few-shot prompting, and the model's own generic output works as the negative. DITTO ("Show, Don't Tell", https://arxiv.org/abs/2406.00888) turned that into a strong small-data method.
- Where a sample came from beats how it reads. Detectors cannot reliably tell AI text from human text after the fact (https://theconversation.com/why-its-so-hard-to-tell-if-a-piece-of-text-was-written-by-ai-even-for-ai-265181), so sort samples by origin.
- One section per format. Practitioner systems (Daria Cupareanu, https://aiblewmymind.substack.com/p/claude-skills-ai-write-like-you; Paul Goldsmith-Pinkham, https://paulgp.substack.com/p/writing-and-thinking-with-ai-assistance) keep separate guidance per format; one guide for every format turns the voice into a caricature.

## Step 1: Sort the writing by where it came from

Record every sample in `voice/samples-index.md`, one line each: an ID, the source, the date, the format, the origin tier below, and whether it is held back. Sort by origin, never by how a sample reads.

**First, write the contrast drafts.** Before you read any sample, list 3 to 5 of the writer's topics from titles or file names alone and draft a piece on each, cold. If a format has no titles (a post export, say), ask the writer for 3 to 5 topic lines instead. These become the AI contrast material; pair each cold draft only with a real piece in the same format, or note that none exists. Once you have read the writer, your drafts are no longer cold.

**Then clean by metadata, then set aside the held-back samples.** Without reading the text, use only length, date and repost flags to drop captions under about 30 words and collapse each recurring series into one sample (see "What counts as one sample" below). If the export has no series field, flag cadence clusters (same weekday and time, regular gaps), confirm a series once you have read the samples you kept, and swap any held-back member of a confirmed series for another sample by ID. If origin can already be decided from metadata (for example the writer's AI start date, asked below), sort by origin first, so the holdout comes from gold: a held-back edited sample tests nothing. Then pick about 20% of each format's gold at random with a script, list their IDs as held back, and never open them until Step 4. Picking after reading leaks them into your judgment.

**Then ask the writer where each sample came from.** Ask them to mark each one "mine", "AI helped" or "unsure". A shortcut: ask roughly when they started using AI on that kind of writing, and treat everything before that date as theirs. Whatever they answer, also flag likely assisted samples yourself (a templated weekly series, a burst of similar posts close together, a sudden jump in length, dashes appearing where they never did, the writer mentioning an assistant). Run every count in Step 2 twice, with and without the flagged samples, and ask the writer about the flagged ones. When the two counts disagree, the rule is provisional: mark it so in the voice file, and ask first about the flagged samples that would flip it.

- **Gold:** [LIST]. Provably the writer's own: writing from before AI tools, dictated notes and transcripts, chat prompts they typed, posts they confirm they wrote unassisted. The only evidence of voice.
- **Edited:** [LIST]. Their ideas with AI or editor polish. Anything that went through an editor or publisher counts here by default. Split mixed sources first: an older piece reprinted inside a newer one is sorted by its own date and can be gold (leave its punctuation, such as dashes and quote marks, out of the counts, because the publisher may have changed it), and other people's words inside it (guest pieces, quotes, Q&A answers) are removed.
- **AI contrast:** [LIST]. Model drafts on the writer's topics, the negative material. If there are none, use the cold drafts from the first step of Step 1.
- **Quarantine:** [LIST]. Origin unknown. Excluded from everything.

**What counts as one sample.** A recurring series (the same template every week) counts as one sample, not one per post. Remove quotes from other people, epigraphs and captions under about 30 words before counting. Decide whether a repost with the writer's own comment counts as a sample, and apply that one way throughout. Note in the index what you removed.

Aim for 10 to 15 gold samples per format: 5 to 8 become examples, and about 20% are held back for Step 4.

## Step 2: Extract patterns with evidence

Run this on gold samples, at least twice on different subsets; with fewer than about 12 gold samples in a format, run the second round on the same samples in a fresh context or with the categories in reverse order (each round finds new patterns; Tiago Forte describes four rounds each finding more, https://fortelabs.com/blog/how-to-create-an-ai-style-guide-write-with-chatgpt-in-your-own-voice/).

```
You are extracting voice patterns from my writing: [N] samples, each
tagged source, date, format. Use only GOLD samples as evidence.

For every pattern you claim:
1. State it as a checkable rule: a count, a percentage, or a yes/no.
2. Quote at least 2 verbatim examples, with their tags.
3. Report frequency as X of N samples. I will re-count it.

Cover separately: openings (first line), endings (last two lines),
sentence length, paragraph and list habits, punctuation, emoji and
formatting, emphasis (capitals, doubled words or punctuation), everyday
word choices (my word versus the generic one), words I start sentences
with, how I write numbers, how I hedge (a guess versus a verdict), what I
use as evidence (stories, my own mistakes, questions), dialogue (quoted
or made up), how I explain terms to the reader, comments about the text
itself, objections I voice and then answer, stock idioms, how I list
items inside a sentence, tics that belong only to speech, signature
phrases, and NEVER-patterns (absent from my writing, common in model
output).

No adjectives (conversational, authentic, engaging); an adjective is
not a rule I can check.
```

Edited material is not wasted: run the same prompt on it to suggest candidate patterns, then keep a candidate only if it also shows up in gold samples. This matters most for long-form, where gold is often scarce.

Then re-count every claim with a script, using fixed definitions so two runs agree: a sentence ends at ".", "!", "?" or a line break; a list line starts with a bullet, a number or an emoji used as a bullet; a contraction spot is any place a contraction could stand ("it is", "I have", "do not" and their contracted forms), and the rate is contracted spots divided by all spots. Before counting, normalise the text: turn styled unicode letters into plain ones and remove leftover export codes for line breaks. Then remove heading lines, @mentions, hashtags, runs of capitalised words and a list the writer gives you of their own product and book names, so a title does not count as the writer using a word; report each count before and after. Some habits (how a piece opens, the analogies it reaches for) cannot be counted by a script: count them by hand with a written coding rule, and record each sample's code in the index so a second pass can check it. Extraction over-claims: a habit the model says shows up in "about half" the samples often turns out to be a quarter or less once you count it.

## Step 3: Write the voice file

Fill `templates/voice-core.md` and save it as `voice-core.md` in the writer's voice folder. If the writer already has a copy of the default voice there, carry its "Personal habits" section over unchanged and replace everything else: the default's habits belong to someone else, so signature moves now come only from the writer's own samples. Add:

- One examples section per format: 5 to 8 full verbatim gold samples with dates and IDs, picked per draft for topic and length. For long-form, use passages of 150 to 400 words cut at paragraph breaks, not whole chapters.
- 2 or 3 contrast pairs on the same topic: the generic model draft labeled NEVER LIKE THIS, the writer's real piece labeled LIKE THIS.
- The writer's exceptions to the ban layer (words and moves the public slop lists flag but this writer really uses), each with its count. A word only becomes an exception with 3 or more uses across at least 2 samples of confirmed unassisted writing; uses from two different years are a further check, not a substitute. A banned sentence shape or structure (ban layer sections 3 and 4) never becomes an exception on counts alone; show the writer the examples and ask, and list it under "Pending the writer's sign-off" until they answer.
- The blanks the samples cannot fill. Some lines need the writer, not their writing: the facts and numbers they are happy to use in public, and what they never want said in public. Ask these as direct questions and write down their answers word for word.

## Step 4: Prove it blind

This step needs a person who knows the writer's work. Until one has done it, mark the voice file "blind test pending" at the top.

- Keep the held-back 20% out of every prompt. Before drafting a held-back topic, write a short fact sheet for it from the writer (what happened, the real numbers), so the draft never has to invent a fact to finish the story. Draft a held-back topic with the voice file, show both texts unlabeled to someone who knows the writer's work, and ask which one the writer wrote. Do 20 or more trials across topics. Pass means the picker is close to chance.
- Compute the voice file's numbers (sentence length, paragraph length, emoji rate and so on) on the drafts and compare them with the held-back samples, not with the examples.
- Never use a model as the main judge of voice; it measures how model-like text is, not how writer-like.

## Step 5: Keep it learning

Follow `learning-loop.md` after every published piece.

## What slop looks like, annotated

A cold model draft on a common topic (the most important habit for a remote team), with each tell tagged by its ban-layer section:

```
After a decade of working on distributed teams, if I had to name the
single habit that matters most, it wouldn't be tooling, rituals, or
time-zone overlap.                          <- 27-word windup; three-part list (3)

It's writing things down.

Not the long, nobody-reads-it kind of documentation. Real writing.
                                             <- "not X, real Y" (3)
Here's what it looks like in practice:      <- setup phrase (2)
...
Here's the thing: most remote failures I've witnessed weren't
communication failures. They were memory failures.
                                             <- "Here's the thing" (2); negative parallelism (3)

Meetings end. Chats scroll away. But a written decision keeps paying
off for years.                              <- stacked minted aphorisms (4)
Agree or disagree?                           <- social-post template (2)

#RemoteWork #Leadership #Documentation #Teams   <- hashtag block (6)
```

A real writer on the same topic would usually get to the point in the first line, name the specific things their team writes down (decisions, handoffs, the one page new hires read first), and end without a slogan.

## Checklist

- [ ] Held-back samples picked by script before reading anything
- [ ] Every sample in voice/samples-index.md with source, date, format and origin; the writer asked to mark origin
- [ ] Series counted once; quotes, epigraphs and short captions removed
- [ ] 10 to 15 gold samples per format; 20% held back, never loaded
- [ ] Extraction run twice or more; every claim re-counted, uncounted claims deleted
- [ ] voice-core.md: numbers, signature moves with counts, bans and exceptions (3+ unassisted uses in 2+ samples) with sources
- [ ] Public facts and never-say lines answered by the writer, not guessed
- [ ] One examples section per format, 5 to 8 full verbatim samples with IDs
- [ ] 2 or 3 contrast pairs on the same topic
- [ ] Blind test: 20 or more trials, picker near chance (or marked "blind test pending")
- [ ] Learning log started
