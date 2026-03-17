# ADR-002 — Uso de Kafka

## Status

Accepted

## Context

Necessidade de comunicação assíncrona entre microsserviços.

## Decision

Utilizar Kafka como broker de eventos.

## Justification

* desacoplamento entre serviços
* alta escalabilidade
* suporte a múltiplos consumidores

## Consequences

* maior complexidade operacional
* necessidade de monitoramento de tópicos
