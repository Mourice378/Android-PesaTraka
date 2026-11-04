# 0002. Use a Melos multi-package monorepo

Status: Accepted
Sprint / card: 0 / FIN-002
Date: 2026-11-04

## Context
Sprint 1 requires that domain code never imports Flutter or dart:ui
(FIN-109). The README's original layout is a single package with folders
(lib/models, lib/services, ...).

## Options considered
A. Melos monorepo: app, domain, data, sync, fake_bank
B. Single Flutter package with folders

## Decision
A. A package boundary makes the dependency rule enforceable: domain's
pubspec simply has no Flutter dependency, so an illegal import cannot
compile. A folder convention can only be checked by discipline.

## Rejected alternative
B. Simple and fine for a small app, but nothing stops a widget importing
a database class, or domain importing Flutter.

## Consequences and cost
More setup (workspace config, per-package pubspecs and analysis options).
fake_bank must live in the same repo as a Dart server.

## Evidence
FIN-109 import-boundary test (to be written in Sprint 1).

## Revisit when
The number of packages grows past what one repo can build in reasonable
CI time, or a package needs its own release cycle.