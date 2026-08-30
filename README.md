# Atom Learning Model (ALM): companion data

Companion repository for **"Atom Learning Model (ALM): how a real classroom
got tokenised"**, arXiv:2608.21106
([abstract](https://arxiv.org/abs/2608.21106), [PDF in this
repository](atom-learning-model.pdf), DOI
[10.48550/arXiv.2608.21106](https://doi.org/10.48550/arXiv.2608.21106)).
The report describes a deployed
tutoring system whose curriculum is a catalogue of 1,934 atoms, small
checkable capabilities, joined by 4,616 typed prerequisite links, on which
questions are composed and children's ability is tracked, atom by atom.

An interactive view of the catalogue being built, page by page from the two
source textbooks, is at **https://philippbogdan.com/atoms**.

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

## Licence

Data and schemas: CC BY 4.0. The report itself is on arXiv under the same
licence: <https://arxiv.org/abs/2608.21106>.
