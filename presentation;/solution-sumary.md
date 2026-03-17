# Solution Summary

A solução automatiza o rastreio de pedidos utilizando integração com a API da transportadora Carriers.

O sistema é baseado em microsserviços e orientado a eventos, garantindo escalabilidade e desacoplamento.

O Tracking Service atua como núcleo da solução, sendo responsável por consultar a API, processar dados e distribuir eventos via Kafka.

Componentes adicionais como Redis, Circuit Breaker e DLQ aumentam a robustez e confiabilidade.

A solução está preparada para ambientes produtivos e crescimento futuro.
