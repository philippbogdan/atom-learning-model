# Atom Learning Model (ALM)

Adaptive mathematics tutoring needs to know which small skills each child
holds and set work just beyond them. ALM reads GCSE and Further Mathematics
material into a map of single-step skills.

ALM composed 6,648 mathematics questions for 373 children in two English
secondary schools over seven weeks, at 26p per composed question for
composition and checking. No one wrote a skill, prerequisite link or question.

Reading 757 pages of GCSE and Further Mathematics material cost £55;
the paper estimates £615 to £1,230 for the whole curriculum structure.
The [released graph, worked examples and schemas](#what-is-here) let
researchers inspect this alternative to expert-built skill maps and
hand-written question templates.

The difficulty labels failed: across 730 measured questions, their rank
correlation with the share answered correctly was −0.0123, effectively zero.

Companion data for [Atom Learning Model (ALM): how a real classroom got
tokenised](atom-learning-model.pdf),
[arXiv:2608.21106](https://arxiv.org/abs/2608.21106), DOI
[10.48550/arXiv.2608.21106](https://doi.org/10.48550/arXiv.2608.21106).
[Interactive companion](https://philippbogdan.com/atoms).

## What is here

Exactly what section 12 of the report promises: enough to inspect the
structures and to rebuild the system's shape, without the things that cannot
be released (children's classroom work, the full catalogue content derived
from two commercial textbooks, the production codebase).

- `data/worked-closure.json`: the report's worked atom,
  `ALGEBRA.SOLVE_LINEAR_SIMULTANEOUS`, with the complete catalogue records of
  its seven-atom prerequisite closure: statements, teaching units,
  misconceptions, actions, typed links, homes.
- `data/worked-template.json`: the real production emission behind section
  7: the composer's template (stem, slots, constraint, verify expression,
  step DAG) and all eight kernel draws the report prints, including
  3x + 6y = 57, 4x − 2y = 16 → x = 7.
- `data/prerequisite-graph.json`: the full graph with content stripped:
  1,934 atoms under opaque identifiers, with domain, home subtopics and
  depth per atom, and all 4,616 typed edges (3,581 prereq, 1,035 derivable;
  one edge per ordered pair, prereq taking precedence for the 28 pairs typed
  both ways). Every structural claim in the report (depth distribution,
  the three cycles, domain modularity) can be checked against this file.
- `schemas/`: the three shapes a builder would target: the atom record,
  the composer's question template, and the marker's credit vector.
- `charts/`: the two agent pipelines as drawn in the report: the six
  bootstrap agents, and the composition-verification-repair loop.

## Rebuilding the run's numbers on your own deployment

A team with their own deployment needs only three tables to rebuild every
number in sections 10 and 11 of the report against their own logs: one row
per attempt (child index, atom, credited or not, when, prior attempts on
that atom, how much of the closure carried evidence at that moment); one row
per question (the atoms it composes, its declared band, compose passes,
cost); one row per session (child index, ordered attempts, the wait for each
mark, whether another attempt followed).

## Assumptions made

- The build bracket is estimated from measured stage shares. Costs use
  list-price model billing, converted at $1.30 to £1, without batching or
  caching.
- The archive does not record how many composed questions reached children.
  Composition and checking cost 26p to £1.10 per answered question.
- The 730 measured questions each had at least five scored attempts; only
  four of those 730 were labelled advanced. Marking accuracy was not
  independently checked.
- Mastery scores were reconstructed afterwards and never drove selection.
  Too few deep questions were served to test whether prerequisite depth and
  missing skills explain difficulty; the premise remains unconfirmed. No
  subject specialist checked the catalogue.

## Licence

Data and schemas: CC BY 4.0. The report itself is on arXiv under the same
licence: <https://arxiv.org/abs/2608.21106>.
