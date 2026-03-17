# Architecture Overview

A solução é baseada em microsserviços e segue um modelo orientado a eventos.

O Tracking Service atua como produtor de eventos, enquanto outros serviços consomem as atualizações via Kafka.

Componentes principais:

* API Gateway
* Scheduler
* Tracking Service
* MongoDB
* Redis
* Kafka
* DLQ
* Observability

A arquitetura garante desacoplamento, escalabilidade e resiliência.
