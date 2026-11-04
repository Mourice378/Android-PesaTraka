# Definition of Done PesaTraka

Applies to every card, in every sprint. A card does not move to Done
until all six checks are true.

1. **Full data.** The feature runs against the full seeded dataset
   (12 accounts, 300k transactions), not a toy fixture.
2. **Failure observed.** The deliberate failure was reproduced and seen
   in a log, a DevTools capture, a trace or a number.
3. **Guard in CI.** An automated check fails if the failure returns, and
   it runs in CI. I reverted the fix once and watched CI go red.
4. **ADR written.** Any non-obvious decision has a one-page ADR in
   [`docs/decisions/`](docs/decisions) that names the alternative I rejected.
5. **Numbers recorded.** Anything measured has its numbers written down,
   not just the conclusion.
6. **Surprises noted.** If something surprised me, it is in a note by the
   end of the day.

## Board rules

- WIP limit of two cards in flight.
- No fix before the failure has been observed.
- Guards stay in CI forever.
- No design polish. Plain Material widgets.

## Commit order that proves it

1. Evidence and failing test (CI red)
2. The fix (CI green)
3. The ADR or note linking both


