# ADR-003 — Uso de Scheduler

## Status

Accepted

## Context

A API da transportadora não fornece eventos push.

## Decision

Utilizar polling via scheduler.

## Justification

* controle total da frequência de consulta
* simplicidade de implementação

## Consequences

* possível latência na atualização
* necessidade de otimização de intervalos
