---
promptId: chainOfDensity
name: 🗞️ Summarize (Chain of Density)
description: select a content and it will be summarized.
author: alexnodeland
tags: prompt
version: 0.0.1
---
**content**: 
{{context}}

**You will generate increasingly concise, entity-dense summaries of the**
**above content.**

**Repeat the following 2 steps 5 times.**

1. Identify 1-3 informative Entities (";" delimited) from the
content which are missing from the previously generated summary.
2. Write a new, denser summary of identical length which covers
every entity and detail from the previous summary plus the Missing
Entities.

**A Missing Entity is**:
- **Relevant**: to the main story.
- **Specific**: descriptive yet concise (5 words or fewer).
- **Novel**: not in the previous summary.
- **Faithful**: present in the content.
- **Anywhere**: located anywhere in the content.

**Guidelines**:
- The first summary should be long (4-5 sentences, -80 words) yet
highly non-specific, containing little information beyond the
entities marked as missing. Use overly verbose language and fillers
(e.g., "this article discusses") to reach -80 words.
- Make every word count: re-write the previous summary to improve
flow and make space for additional entities.
- Make space with fusion, compression, and removal of uninformative
phrases like "the content discusses".
- The summaries should become highly dense and concise yet
self-contained, e-g., easily understood without the content.
- Missing entities can appear anywhere in the new summary.
- Never drop entities from the previous summary. If space cannot be
made, add fewer new entities.

**Remember, use the exact same number of words for each summary.**

Answer in JSON. The JSON should be a list (length 5) of dictionaries
whose keys are "Missing _Entities" and "Denser_Summary".