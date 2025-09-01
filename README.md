# EMS AlgaSensors Meta

Sistema de monitoramento de sensores de algas baseado em microserviços para gerenciamento de dispositivos e processamento de dados de temperatura.

> **📚 Projeto de Estudo**: Este é um projeto criado durante o desenvolvimento do curso **Especialista em Microserviços** da [AlgaWorks](https://www.algaworks.com/).

## 📋 Visão Geral

O EMS AlgaSensors Meta é um projeto de monitoramento ambiental que utiliza uma arquitetura de microserviços para coletar, processar e gerenciar dados de sensores de algas. O sistema é projetado para monitorar condições ambientais, especialmente temperatura, através de dispositivos IoT.

Este projeto foi desenvolvido como parte do aprendizado prático de conceitos de microserviços, incluindo comunicação assíncrona e processamento de dados em tempo real.

## 🏗️ Arquitetura

O projeto segue uma arquitetura de microserviços com os seguintes componentes:

### Microserviços

- **device-management**: Gerenciamento de dispositivos IoT e sensores
- **temperature-monitoring**: Monitoramento em tempo real de dados de temperatura
- **temperature-processing**: Processamento e análise de dados de temperatura

### Infraestrutura

- **RabbitMQ**: Sistema de mensageria para comunicação entre microserviços
- **Docker Compose**: Orquestração de containers para desenvolvimento local

## 🚀 Como Executar

### Pré-requisitos

- Docker
- Docker Compose
- Git

### Instalação

1. Clone o repositório:
```bash
git clone <repository-url>
cd ems-algasensors-meta-main
```

2. Inicialize os submódulos Git:
```bash
git submodule update --init --recursive
```

3. Execute o RabbitMQ:
```bash
docker-compose up -d
```

### Acessando o RabbitMQ Management

- URL: http://localhost:15672
- Usuário: `rabbitmq`
- Senha: `rabbitmq`

## 📁 Estrutura do Projeto

```
ems-algasensors-meta-main/
├── configs/
│   └── rabbitmq/
│       └── enabled_plugins
├── microservices/
│   ├── device-management/
│   ├── temperature-monitoring/
│   └── temperature-processing/
├── docker-compose.yaml
└── README.md
```

## 🔧 Configuração

### RabbitMQ

O RabbitMQ está configurado com os seguintes plugins habilitados:
- `rabbitmq_management`: Interface de gerenciamento web
- `rabbitmq_shovel`: Transferência de mensagens entre brokers
- `rabbitmq_shovel_management`: Gerenciamento de shovels via interface web

### Portas

- **5672**: AMQP protocol (RabbitMQ)
- **15672**: RabbitMQ Management UI

## 🛠️ Desenvolvimento

### Submódulos Git

Este projeto utiliza submódulos Git para gerenciar os microserviços:

- `microservices/temperature-monitoring`: https://github.com/Andre-devel/ems-algasensors-temperature-monitoring.git
- `microservices/device-management`: https://github.com/Andre-devel/ems-algasensors-device-management.git
- `microservices/temperature-processing`: https://github.com/Andre-devel/ems-algasensors-temperature-processing.git

### Atualizando Submódulos

```bash
git submodule update --remote
```

## 📊 Monitoramento

O sistema inclui:
- Monitoramento de temperatura em tempo real
- Gerenciamento de dispositivos IoT
- Processamento de dados ambientais
- Interface de gerenciamento via RabbitMQ
