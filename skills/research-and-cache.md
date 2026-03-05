---
name: research-and-cache
description: Look up historical facts from primary sources and cache the results locally for future conversations
---

When an agent needs to verify a specific fact, quote, date, or detail about a historical figure's life and works, use this skill to research it and cache the findings.

## 1. Check the Cache First

Before doing any web research, check whether the topic has already been researched:

```
${CLAUDE_PLUGIN_ROOT}/cache/<person_name>/<topic>.md
```

Where `<person_name>` is the figure's name in snake_case (e.g., `leonardo_da_vinci`) and `<topic>` is a short descriptive slug (e.g., `last_supper_details`, `letter_to_lodovico`, `mirror_writing`).

If a cache file exists and covers the needed information, use it directly. Do not re-research.

## 2. Research from Primary Sources

If the cache does not contain what is needed, use the Playwright browser to look up the topic. Prioritize these source types in order:

1. **Project Gutenberg** (gutenberg.org) -- full texts of published works, letters, and translations
2. **Wikipedia** -- for factual summaries, dates, and cross-references (verify key claims against other sources when possible)
3. **Academic and archival sources** -- university digital libraries, museum collection pages, scholarly articles
4. **Archive.org** -- digitized primary texts, historical documents, out-of-print books

Focus your research on:
- Direct quotes from the figure's own writings, letters, or documented speech
- Specific dates, locations, and verifiable facts
- Context that helps an agent respond authentically (e.g., what was happening in their life at a given time)

Avoid:
- Blog posts, listicles, or unsourced quote collections
- Paraphrased or heavily interpreted secondary sources when primary sources are available
- Overly broad searches -- keep queries specific to the fact in question

## 3. Cache the Findings

Save your research as a markdown file at:

```
${CLAUDE_PLUGIN_ROOT}/cache/<person_name>/<topic>.md
```

Create the person's directory if it does not exist.

A good cache entry includes:

```markdown
# <Topic Title>

## Summary
A brief 2-3 sentence summary of the key finding.

## Primary Source Quotes
Direct quotes with attribution:
- "Quote text here." -- Source title, date/location if known

## Key Facts
- Fact 1 with date or context
- Fact 2
- Fact 3

## Sources
- [Source title](URL) -- brief note on what was found there
```

### Guidelines for cache entries:

- **Prefer direct quotes over paraphrases.** The whole point is to ground agent responses in documented words.
- **Include attribution.** Note which notebook, letter, book, chapter, or speech a quote comes from.
- **Date when possible.** Knowing when something was written helps agents place it in their own timeline.
- **Keep entries focused.** One topic per file. A cache entry about Einstein's letters to Besso should not also cover his Nobel Prize speech.
- **Note conflicting sources.** If sources disagree on a fact, document the disagreement rather than picking one.

## 4. Use Cached Results

After caching, return to the conversation and use the findings to inform the agent's response. Cite specifics naturally in character -- the agent should weave verified facts and quotes into their dialogue without breaking the conversational tone.
