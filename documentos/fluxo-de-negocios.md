# Business Flow

## Overview

O fluxo de negócio descreve como o sistema processa atualizações de rastreio desde a origem (transportadora) até o consumo pelos serviços internos.

---

## End-to-End Flow

1. Scheduler dispara execução periódica
2. Tracking Service seleciona pedidos a serem atualizados
3. Serviço consulta API da Carriers
4. Dados retornados são normalizados
5. Sistema verifica duplicidade de eventos
6. Se houver alteração:

   * Atualiza MongoDB
   * Atualiza Redis Cache
   * Publica evento no Kafka
7. Serviços consumidores recebem o evento
8. Em caso de falha no consumo, evento é enviado para DLQ

---

## Business Rules

* Eventos não devem ser duplicados
* Apenas mudanças relevantes devem gerar publicação
* Pedidos entregues podem ter ciclo de rastreio encerrado
* Falhas devem ser registradas e reprocessáveis

---

## Key Benefits

* redução de trabalho manual
* atualização em tempo quase real
* desacoplamento entre serviços
* escalabilidade horizontal
