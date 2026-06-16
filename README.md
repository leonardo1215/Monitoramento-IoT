# 🌐 Sistema de Monitoramento IoT com ESP32, MQTT e Node-RED

## 📋 Descrição

Este projeto consiste em um sistema de monitoramento IoT desenvolvido utilizando **ESP32**, **MQTT**, **Node-RED** e **Dashboard Web**, permitindo acompanhar sensores em tempo real e controlar dispositivos remotamente.

Os dados de temperatura, umidade e luminosidade são coletados pelo ESP32, enviados via protocolo MQTT para um broker público e exibidos em um painel interativo desenvolvido no Node-RED.

Além do monitoramento, o sistema possui um alarme sonoro (buzzer) que pode ser ativado ou silenciado diretamente pelo Dashboard.

---

## 🚀 Tecnologias Utilizadas

* ESP32
* Arduino IDE / C++
* Wokwi Simulator
* MQTT (HiveMQ Broker)
* Node-RED
* Node-RED Dashboard
* DHT22
* Sensor de Luminosidade (LDR)
* Display OLED SSD1306

---

## ⚙️ Funcionalidades

### Monitoramento em tempo real

* 🌡️ Temperatura
* 💧 Umidade
* 💡 Luminosidade
* 🚨 Status do ambiente (NORMAL, ATENÇÃO e CRÍTICO)

### Interface Web

Dashboard desenvolvido no Node-RED contendo:

* Cards de resumo
* Gauges em tempo real
* Indicador visual de status
* Histórico da temperatura
* Histórico da umidade
* Histórico da luminosidade
* Barra de status do sistema
* Botões para controle do alarme

### Controle Remoto

O Dashboard envia comandos MQTT para o ESP32 permitindo:

* 🔕 Silenciar Alarme
* 🔔 Ativar Alarme

---

## 📡 Comunicação MQTT

### Publicação

Tópico utilizado para envio dos dados:

```
leonardo/iot/monitoramento/dados
```

Payload enviado:

```json
{
  "temperatura": 28.5,
  "umidade": 55.2,
  "luminosidade": 2300,
  "status": "NORMAL",
  "buzzer": "DESLIGADO"
}
```

### Assinatura

Tópico utilizado para comandos:

```
leonardo/iot/monitoramento/comando
```

Comandos aceitos:

```
ATIVAR
SILENCIAR
```

---

## 🔧 Hardware Utilizado

* ESP32 DevKit V1
* Sensor DHT22
* Sensor LDR
* Display OLED SSD1306 I2C
* LED Verde
* LED Amarelo
* LED Vermelho
* Buzzer

---

## 📊 Dashboard

O Dashboard apresenta:

* Barra superior de status
* Cards de informações rápidas
* Indicadores analógicos (Gauges)
* Status visual do ambiente
* Gráficos históricos
* Controle do alarme

Interface totalmente responsiva para computadores e dispositivos móveis.

---

## 🎯 Lógica do Sistema

### NORMAL

* LED Verde ligado
* Buzzer desligado

### ATENÇÃO

* LED Amarelo ligado
* Monitoramento intensificado

### CRÍTICO

* LED Vermelho ligado
* Buzzer acionado
* Possibilidade de silenciamento remoto pelo Dashboard


## 👨‍💻 Autor

Projeto desenvolvido por **Leonardo** como estudo prático de Internet das Coisas (IoT), integração MQTT e desenvolvimento de dashboards utilizando Node-RED.

---

## 📜 Licença

Este projeto é disponibilizado para fins acadêmicos e educacionais, podendo ser utilizado como base para estudos e futuras implementações em sistemas IoT.
