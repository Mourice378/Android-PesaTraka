# 0001. Build PesaTraka, an offline-first personal-finance app

Status: Accepted
Sprint / card: 0 / FIN-002
Date: 2026-11-04

## Context
I want a project where concurrency, sync, money correctness and security
failures happen naturally instead of being staged. <br>
Prediction: a finance app forces all of them, because money has hard invariants.

## Options considered
A. Offline-first personal-finance app (PesaTraka)<br>
B. Media / streaming app

## Decision
A. Failures like double charge, lost update and negative balance are
business bugs with an unambiguous pass/fail test.

## Rejected alternative
B. Its failures are mostly caching and bandwidth. There is no invariant
to defend, so the automated guards would be softer.

## Consequences and cost
I must model money correctly and build a fake bank API (fake_bank).
More backend work than a pure client app.

## Evidence
Coverage matrix (Appendix A of the guide) maps every topic to a sprint.

## Revisit when
The guide's topics stop mapping onto this domain.