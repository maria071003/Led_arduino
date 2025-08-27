# Led_arduino
#  Projeto: Acendendo um LED com ESP32

Este projeto mostra passo a passo como montar um circuito simples com ESP32 para acender um LED, utilizando uma protoboard, resistor e jumpers. Cada passo está documentado com imagens reais para facilitar a reprodução por iniciantes.

---

## Materiais Utilizados

- 1x ESP32 DevKit V1
- 1x LED (vermelho)
- 1x Resistor 220Ω ou 330Ω
- 1x Protoboard
- 2x Jumpers macho-macho
- 1x Cabo USB

---

##  Passo a Passo com Imagens

---

###  Etapa 1: Visão geral dos componentes

![Etapa 1](./images/WhatsApp%20Image%202025-08-27%20at%2013.21.06.jpeg)

> Nessa imagem temos o ESP32, protoboard, LED, resistor e cabos jumper que serão utilizados no projeto.

---

###  Etapa 2: ESP32 inserido na protoboard

![Etapa 2](./images/WhatsApp%20Image%202025-08-27%20at%2013.21.06%20(1).jpeg)

- O ESP32 foi encaixado no meio da protoboard.
- Certifique-se de que os pinos não fiquem curtos entre si.
- Deixe espaço nas laterais para os jumpers.

---

###  Etapa 3: ESP32 fora da protoboard

![Etapa 3](./images/WhatsApp%20Image%202025-08-27%20at%2013.21.06%20(2).jpeg)

> Visualize os pinos com clareza. Você usará:
- `GPIO 23` para controlar o LED
- `GND` para o terra do circuito

---

###  Etapa 4: LED e resistor conectados

![Etapa 4](./images/WhatsApp%20Image%202025-08-27%20at%2013.21.06%20(3).jpeg)

- Conecte o **ânodo (perna longa)** do LED ao `GPIO 23` do ESP32
- Conecte o **cátodo (perna curta)** a um resistor
- O outro lado do resistor vai para o trilho azul da protoboard (GND)

---

### 📷 Etapa 5: Conectando o GND do ESP32

![Etapa 5](./images/WhatsApp%20Image%202025-08-27%20at%2013.21.06%20(4).jpeg)

- Conecte o pino `GND` do ESP32 ao **trilho azul da protoboard**
- Isso fecha o circuito do LED

---

### 📷 Etapa 6: Checagem final antes do upload

![Etapa 6](./images/WhatsApp%20Image%202025-08-27%20at%2013.21.06%20(5).jpeg)

> Confira todas as conexões:
- GPIO 23 -> LED -> Resistor -> GND
- GND do ESP32 conectado ao trilho azul

---

### 📷 Etapa 7: Subindo o código via USB

![Etapa 7](./images/WhatsApp%20Image%202025-08-27%20at%2013.21.06%20(6).jpeg)

Abra a **Arduino IDE**, conecte o ESP32 e cole o seguinte código:

```cpp
int ledPin = 23;

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  digitalWrite(ledPin, HIGH);
  delay(1000);
  digitalWrite(ledPin, LOW);
  delay(1000);
}
