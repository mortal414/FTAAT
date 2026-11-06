# Original FTAAT design

I originally used synthetic key-value associations to explore how language models handle information supplied in a prompt. This page describes that older idea; the paid notebook runner is retired.

A trial supplies records such as `A|B|C => X|Y|Z`, then asks for the values in a different order. The original experiments varied the number of records (`N`) and the number of pipe-delimited symbols in each key and value (`K`).

## What needed correcting

- **Symbols are not model tokens.** A string can tokenize differently when joined with other strings and delimiters. `K` is a symbol count, not a guaranteed BPE-token count.
- **The result is task performance, not a direct memory measurement.** Prompt length, answer length, formatting, output limits and scoring all matter. The experiment does not isolate internal attention or establish a universal context limit.
- **Missing answers must count.** The original grading and batch-matching behavior could make comparisons misleading. Historical results need re-auditing and are not combined with the later experiments.
- **Provider integrations differed.** The old adapters and inventory files do not establish equivalent tokenization or verified support across providers.

## Where to look now

The [methodology](methodology.md) describes the later runner's full-request counts, deterministic cases, separate error categories and budget accounting. The [second-edition report](episodes/01-v2/report.md) contains the recorded results and their limits. The [README](../ReadME.md) explains how to inspect the saved material.

The old notebooks and helper modules remain for reference, not as a maintained testing service.
