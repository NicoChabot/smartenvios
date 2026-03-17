# Tracking Sequence

## Sequence Flow

1. Scheduler inicia execução
2. Tracking Service consulta API externa
3. API retorna eventos
4. Serviço normaliza dados
5. Verifica duplicidade
6. Atualiza MongoDB
7. Publica evento no Kafka
8. Consumidores processam evento
9. Falhas são enviadas para DLQ

## Observação

Este fluxo representa o ciclo completo de atualização de rastreio.
