DC Watch IoT

Sistema de monitoramento inteligente para racks e ambientes de Data Center utilizando ESP32, MQTT, Node-RED e Telegram.

Visão Geral

O DC Watch IoT foi desenvolvido para monitorar variáveis críticas de um rack de Data Center em tempo real.

O sistema coleta informações dos sensores conectados ao ESP32, transmite os dados via MQTT para o Node-RED e exibe tudo em dashboards web responsivos.

Além disso, o sistema registra histórico dos dados e envia alertas automáticos via Telegram quando condições críticas são detectadas.

Arquitetura
ESP32
 │
 ├─ Sensores
 │
 ├─ MQTT
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
Tecnologias Utilizadas
Hardware
ESP32
DHT22
DS18B20
Sensor PIR
Sensor de fumaça
OLED SSD1306
LCD 16x2 I2C
Servo Motor
LEDs de status
Buzzer
Botões
Potenciômetros (simulação)
Software
Arduino IDE
ESP32
MQTT
Mosquitto Broker
Node-RED
Dashboard 2.0
Telegram Bot API
Wokwi Simulator
Funcionalidades
Dashboard Principal

Monitoramento em tempo real:

Temperatura ambiente
Temperatura do rack
Umidade
Luminosidade
Consumo
Fumaça

Indicadores de infraestrutura:

Porta
Energia
Movimento
Ventilação

Status geral do rack:

NORMAL
ATENÇÃO
CRÍTICO
Dashboard Histórico

Registro dos últimos eventos recebidos.

Exibe:

Temperatura ambiente
Temperatura do rack
Umidade
Consumo
Fumaça
Status geral

Inclui:

Gráficos históricos
Tabela de registros
Atualização em tempo real
Alertas Telegram

Envio automático de notificações quando limites críticos são atingidos.

Exemplos:

🚨 ALERTA DC WATCH

Rack: rack01

💨 Fumaça Detectada: 84%

🕒 22/06/2026 21:11:15
🚨 ALERTA DC WATCH

Rack: rack01

🔥 Temperatura Rack Alta: 38.6°C

🕒 22/06/2026 21:12:56
Fluxo MQTT

Tópico utilizado:

dcwatch/rack01/telemetry

Payload:

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
Estrutura do Projeto
ESP32
├── Leitura de sensores
├── Controle local
├── LCD 16x2
├── OLED SSD1306
└── MQTT Publisher

Node-RED
├── Dashboard Principal
├── Dashboard Histórico
├── Armazenamento em memória
├── Processamento de dados
└── Telegram Alerts
Simulação

O projeto foi desenvolvido e validado utilizando:

Wokwi Simulator

permitindo testes completos sem necessidade do hardware físico.

Autor

Leonardo Camargo

Projeto desenvolvido para estudo e demonstração de competências em:

IoT
Automação
Node-RED
MQTT
ESP32
Monitoramento Industrial
Data Centers
