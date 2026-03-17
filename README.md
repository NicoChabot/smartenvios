# SmartEnvios — Sistema de Rastreio Automatizado com Carriers

## 📌 Visão Geral

Este projeto propõe uma arquitetura de microsserviços para automatizar o rastreio de pedidos utilizando a API da transportadora **Carriers**.

A solução elimina processos manuais, melhora a escalabilidade do sistema e permite a distribuição de eventos de rastreio em tempo real para serviços internos.

---

## 🎯 Problema

Atualmente, o rastreio de pedidos depende de consultas manuais ou integrações limitadas, gerando:

* atraso na atualização de status
* alto esforço operacional
* acoplamento entre sistemas
* baixa escalabilidade

---

## 💡 Solução Proposta

A solução consiste em um **Tracking Service** que:

* consulta periodicamente a API da transportadora
* normaliza os dados
* evita duplicidade de eventos
* persiste os dados em MongoDB
* publica eventos no Kafka
* distribui atualizações para outros microsserviços

---

## 🏗️ Arquitetura

A arquitetura é composta por:

* API Gateway
* Scheduler
* Tracking Service
* MongoDB
* Redis Cache
* Kafka
* Kafka DLQ
* Notification Service
* Dashboard Service
* Observability Stack

---

## 🔄 Fluxo da Solução

1. Scheduler dispara o processo
2. Tracking Service consulta a API Carriers
3. Dados são normalizados
4. Sistema verifica duplicidade
5. Dados são persistidos no MongoDB
6. Eventos são publicados no Kafka
7. Serviços consumidores processam os eventos
8. Falhas são enviadas para DLQ

---

## 🗄️ Modelo de Dados

```json
{
  "trackingCode": "SM82886187440BM",
  "carrier": "Carriers",
  "currentStatus": "Entregue",
  "events": [
    {
      "timestamp": "2025-01-20T10:30:00Z",
      "status": "Em trânsito",
      "location": "São Paulo, SP"
    }
  ]
}
```

---

## 📡 Comunicação

* HTTP → integração com API externa
* Kafka → comunicação assíncrona entre serviços

---

## 📊 Observabilidade

A solução contempla:

* logs estruturados
* métricas operacionais
* tracing distribuído
* monitoramento de falhas

---

## 🛡️ Resiliência

* Circuit Breaker
* Retry com backoff
* Timeout configurável
* DLQ para mensagens com erro

---

## ⚡ Performance

* Redis para cache
* índices no MongoDB
* processamento incremental

---

## 📦 Estrutura do Projeto

```
docs/
diagrams/
examples/
presentation/
```

---

## 🧠 Decisões Técnicas

* MongoDB → flexibilidade e performance
* Kafka → desacoplamento e escalabilidade
* Redis → otimização de leitura
* Microsserviços → modularidade e manutenção

---

## ✅ Critérios de Aceite

* diagrama de arquitetura definido
* fluxo documentado
* endpoints especificados
* modelo de dados definido
* tópicos Kafka documentados

---

## 🚀 Próximos Passos

* implementação do serviço
* deploy em ambiente cloud
* integração com sistema real
* monitoramento em produção

---

## 👨‍💻 Autor
Nicolás Melo Chabot  
Software Engineer | FullStack | Backend & AI  
LinkedIn: [Linkedin](https://www.linkedin.com/in/nicol%C3%A1s-melo-chabot-6608831a2/)  
GitHub: [Github](https://github.com/NicoChabot)
Projeto desenvolvido como solução técnica para desafio de arquitetura de microsserviços.
