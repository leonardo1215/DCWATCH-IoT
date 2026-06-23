# 🚨 DC Watch IoT

Sistema de monitoramento inteligente para racks e ambientes de Data Center utilizando ESP32, MQTT, Node-RED e Telegram.

---

## 📖 Visão Geral

O **DC Watch IoT** foi desenvolvido para monitorar variáveis críticas de um rack de Data Center em tempo real.

O sistema coleta informações dos sensores conectados ao ESP32, transmite os dados via MQTT para o Node-RED e exibe tudo em dashboards web responsivos.

Além disso, o sistema registra histórico dos dados e envia alertas automáticos via Telegram quando condições críticas são detectadas.

---

## 🏗️ Arquitetura

```text
ESP32
 │
 ├─ Sensores
 │
 ├─ MQTT Publisher
 │
 ▼
Broker MQTT
 │
 ▼
Node-RED
 │
 ├─ Dashboard Principal
 ├─ Dashboard Histórico
 ├─ Registro de Eventos
 └─ Alertas Telegram
```

---

## ⚙️ Tecnologias Utilizadas

### Hardware

- ESP32
- DHT22
- DS18B20
- Sensor PIR
- Sensor de Fumaça
- OLED SSD1306
- LCD 16x2 I2C
- Servo Motor
- LEDs de Status
- Buzzer
- Botões
- Potenciômetros

### Software

- Arduino IDE
- MQTT
- Mosquitto Broker
- Node-RED
- Dashboard 2.0
- Telegram Bot API
- Wokwi Simulator

---

## 📊 Funcionalidades

### Dashboard Principal

Monitoramento em tempo real de:

- Temperatura Ambiente
- Temperatura do Rack
- Umidade
- Luminosidade
- Consumo
- Fumaça

Indicadores de infraestrutura:

- Porta
- Energia
- Movimento
- Ventilação

Status Geral:

- NORMAL
- ATENÇÃO
- CRÍTICO

---

### 📈 Dashboard Histórico

Registro contínuo dos eventos recebidos.

Exibe:

- Temperatura Ambiente
- Temperatura Rack
- Umidade
- Consumo
- Fumaça
- Status Geral

Recursos:

- Gráficos em tempo real
- Histórico dos últimos registros
- Atualização automática

---

### 📲 Alertas Telegram

Envio automático de notificações quando limites críticos são atingidos.

Exemplo:

```text
🚨 ALERTA DC WATCH

Rack: rack01

💨 Fumaça Detectada: 84%

🕒 22/06/2026 21:11:15
```

Outro exemplo:

```text
🚨 ALERTA DC WATCH

Rack: rack01

🔥 Temperatura Rack Alta: 38.6°C

🕒 22/06/2026 21:12:56
```

---

## 📡 MQTT

### Tópico

```text
dcwatch/rack01/telemetry
```

### Payload

```json
{
  "tempAmb": 26.7,
  "tempRack": 18.0,
  "umidade": 8,
  "fumaca": 0,
  "consumo": 49,
  "luminosidade": 84,
  "porta": "FECHADA",
  "energia": "OK",
  "movimento": "NORMAL",
  "ventilacao": "DESLIGADA",
  "status": "NORMAL"
}
```

---

## 🔄 Fluxo do Sistema

```text
ESP32
  ↓
MQTT Broker
  ↓
Node-RED
  ├── Dashboard Principal
  ├── Dashboard Histórico
  ├── Processamento de Dados
  └── Alertas Telegram
```

---

## 🧪 Ambiente de Simulação

O projeto foi desenvolvido e validado utilizando:

- Wokwi Simulator
- Node-RED Dashboard 2.0
- MQTT Broker

Permitindo testes completos sem necessidade de hardware físico.

---

## 👨‍💻 Autor

**Leonardo Camargo**

Projeto desenvolvido para estudo e demonstração de competências em:

- Internet das Coisas (IoT)
- ESP32
- MQTT
- Node-RED
- Automação
- Monitoramento Industrial
- Data Centers
- Sistemas Embarcados

---

## 📷 Demonstração

### Protótipo ESP32

<img width="639" height="590" alt="LINKEDIN PROTOTIPO" src="https://github.com/user-attachments/assets/3ab2bc03-439b-44e5-928f-7e2a9150a717" />


### Fluxo Node-RED

<img width="933" height="348" alt="LINKEDIN NODE RED" src="https://github.com/user-attachments/assets/107bd4a8-ee01-4342-bf11-4df8f8f40b4d" />


### Dashboard Principal
<img width="1885" height="913" alt="linkedin painel" src="https://github.com/user-attachments/assets/93932bfa-a3a3-49be-93c4-7f9b8b9da20d" />


### Dashboard Histórico

<img width="1886" height="917" alt="History painel Linkedin" src="https://github.com/user-attachments/assets/0a04f2ea-df62-413a-83ab-db70c41b8aed" />


### Alertas Telegram

<img width="776" height="1600" alt="dcwatch telegram" src="https://github.com/user-attachments/assets/b672f630-8315-4e5a-a860-35cd39e19255" />
