# ADR-004 — Redis e Resiliência

## Status

Accepted

## Context

Necessidade de melhorar performance e proteger integração externa.

## Decision

Utilizar Redis e padrões de resiliência.

## Justification

* cache reduz carga no banco
* circuit breaker evita falhas em cascata
* retry melhora taxa de sucesso

## Consequences

* aumento da complexidade
* necessidade de tuning
