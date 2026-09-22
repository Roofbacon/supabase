# Voice and tone

Our voice and tone are clean and straightforward. Elegant prose is succinct: it brings a
reader to understanding without spending extra words.

Apply this document to every sentence you write, whether you're drafting a page or changing one line on an existing one.

It covers the sentence level. For how a page divides into sections, see
[`02-page-structure.md`](./02-page-structure.md). For which component renders a piece
of information, see [`03-elements.md`](./03-elements.md).

| If you're deciding                       | Read                                            |
| ---------------------------------------- | ----------------------------------------------- |
| How to mentally frame how you write      | [Audience](#audience)                           |
| How to write sharper and more succinctly | [Brevity](#brevity)                             |
| How to write consistently and correctly  | [Sentence construction](#sentence-construction) |

## Audience

**Write for the reader.** The reader is a developer with a job to do, arriving
mid-task from a search result rather than from the top of the page. Their Postgres
experience ranges from none to deep, and they may be evaluating Supabase or already
running it in production. Think about the task they came to complete. Tell them what,
and only what, they need to know to finish it.

**Write for a massive global audience.** Many readers have a native language that
isn't English. Conversational, direct English is easier to understand, localize, and
read aloud.

**Write for a human and an LLM at once.** Both read our pages. Some principles overlap
while others don't. For a human, be kind and respect their free will. For an LLM, you
may need to nudge it to choose the best practice. Use clean procedures and lots of
code examples to make the best path the easiest choice.

**Write like you talk.** Many readers who use English as an additional language learn
conversational rather than academic English. Use words and sentences that sound
natural when spoken. Read your writing out loud to find the clearest phrasing.

**Avoid idioms and colloquialisms.** A phrase like `piece of cake` is often specific
to a region or culture.

**Address the reader as `you`.** Don't use `we` to refer to the reader. Use `we` only
to refer to the Supabase team.

## Brevity

**Prefer short, direct sentences.** Express one relationship at a time and avoid
unnecessary compound structures. Each sentence gets easier to understand, localize,
and interpret consistently.

**Omit needless words.** Cut every word that does no work. The replacements below
recur often enough to be worth memorizing.

| Wordy                          | Direct   |
| ------------------------------ | -------- |
| the question as to whether     | whether  |
| is able to, has the ability to | can      |
| in the event that              | if       |
| at this point in time          | now      |
| make a decision about          | decide   |
| provides support for           | supports |

**Cut repeated points.** If you can remove a sentence without losing information,
remove it. Watch for a section that restates what an earlier section established, and
for three phrasings of one idea: `It's free`, `You won't be billed`, `No charge`.

**Use the positive form.** State what something does. A positive sentence is shorter
and tells the reader what to do next.

- **Recommended**: `Use an admonition when a reader might otherwise miss information that affects their outcome.`
- **Not recommended**: `Don't use an admonition unless a reader might otherwise miss information that affects their outcome.`

**Cut mannered prose.** Some sentences exist to sound composed. They carry nothing,
and these three are the common shapes:

- **Antithesis.** `X, not Y`, where Y is the negation of X. The negative half feels
  balanced and adds no information, and the sentence after it usually explains the
  point properly anyway. Delete the half after the comma and check whether anything
  was lost.
- **Rhythm for its own sake.** Three examples where two would do, or a clause added to
  balance a sentence.
- **The aphoristic closer.** A final sentence that restates the paragraph in a
  tidier shape. The paragraph already said it.

Contrast is worth keeping when both halves are real and the reader needs the
comparison, as in a recommended and not-recommended pair or a concrete substitution
like `select` rather than `SELECT`.

- **Recommended**: `Write alt text that describes the image. A topic name is what the nearby heading already says.`
- **Not recommended**: `Write alt text that describes the image, not the topic.`

**Be specific and concrete.** A vague verb makes the reader guess at the operation.
Name the operation instead.

- **Recommended**: `Create, edit, and delete tables in the Table Editor.`
- **Not recommended**: `Manage your tables in the Table Editor.`

[`WORD_LIST.md`](./WORD_LIST.md) lists the vague verbs that come up most often. The
principle extends past that list: if a verb could describe five different operations,
it's the wrong verb.

**Keep coordinate ideas parallel.** List items and procedure steps are coordinate
ideas, so give them the same grammatical form. A step list that mixes imperatives with
descriptions reads as though the steps do different kinds of work.

- **Recommended**: `Install the CLI`, `Start the local stack`, `Apply the migration`
- **Not recommended**: `Install the CLI`, `The local stack starts next`, `Applying the migration`

**Put the emphatic words at the end of the sentence.** The end of a sentence is where
a reader's attention lands, so put the consequence there rather than in the middle.

- **Recommended**: `A table with Row Level Security enabled and no policy returns no rows to every client.`
- **Not recommended**: `Every client gets no rows back from a table that has Row Level Security enabled and no policy, which is worth knowing.`

## Sentence construction

**Cover one topic in each paragraph.** Start a new paragraph when the topic changes,
or when you move between [information types](./02-page-structure.md). Short
paragraphs are fine.

**Use complete sentences by default.** They identify the actor and the action, which
reduces ambiguity for readers, translators, and agents. Use sentence fragments only
where they improve scanning, such as headings, labels, or short list items.

**Don't rely on a heading to carry meaning.** Headings guide the reader's eye and
organize the page, but the content beneath one has to stand on its own. The first
sentence can restate the heading, even if that sounds redundant. Readers skim headings
and then return to the section that interests them, so the opening sentence is what
confirms they're in the right place.

**Keep important information out of parentheses.** Some readers skip anything
parenthesized, so a step they need can't live there. Google's
[parentheses guidance](https://developers.google.com/style/parentheses) is the rule we
follow; the cases below come up most in Supabase docs.

Reach for parentheses when the content is brief and genuinely supplementary:

- Introducing an acronym after spelling it out: `full-text search (FTS)`
- Marking an item `(Optional)`
- A short example inside a step: ``Enter a six-digit hex number (for example, `228B22`), and then select **OK**.``

Rewrite as a separate sentence when the aside grows past a few words, or when it
carries something the reader has to act on:

- **Recommended**: ``Enter a six-digit hex number, and then select **OK**. For example, for forest green, enter `228B22`.``
- **Not recommended**: ``Enter a six-digit hex number (for example, if you want the color forest green, enter `228B22`), and then select **OK**.``

Don't use parentheses for optional plurals. Write `one or more tables`, not
`table(s)`. Parentheses required by Markdown links or code syntax aren't prose
parentheticals.

**Don't bound an aside with dashes where a direct sentence reads better.** A pair of
dashes interrupts the sentence the same way parentheses do, and the interruption is
usually a second sentence trying to escape. Google allows a dash in place of
parentheses; Supabase docs prefer the separate sentence.

- **Recommended**: `Don't add steps to reach a minimum. The range organizes information; it isn't a required length.`
- **Not recommended**: `Don't add steps to reach a minimum — the range organizes information, it isn't a required length.`

**Use the Oxford comma.** Write `functions, tables, and indexes`.

**Use American English.** Write `color, organize, center, and artifact`.

**Use the present tense.** Write `the AI assistant answers your question` rather than
`the AI assistant will answer your question`.
