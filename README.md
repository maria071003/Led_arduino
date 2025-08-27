#  Projeto: Acender um LED com ESP32 - Passo a Passo com Imagens

Tutorial prático e ilustrado para montar um circuito básico com ESP32 e acender um LED via código.  
Ideal para iniciantes em eletrônica e Internet das Coisas (IoT).

---

#  Materiais Utilizados

- ESP32 
- Protoboard
- LED 
- Resistor 220Ω
- Jumpers (fios)
- Cabo USB
- Arduino IDE

---

## ESP32 e Protoboard separados

Antes de iniciar a montagem, observe o ESP32 e a protoboard ainda não conectados.

![01 - ESP32 e protoboard](![1 img](https://github.com/user-attachments/assets/5521b7c2-7e0c-4061-a518-3937f3423371)
)

---

## 2️⃣ ESP32 encaixado na protoboard

Insira o ESP32 no centro da protoboard, com espaço livre nas laterais para conectar os fios e componentes.

![02 - ESP32 encaixado](![2 img](https://github.com/user-attachments/assets/f7d46853-183e-42b3-8aa7-65a12c6bf3a9)
)

---

## 3️⃣ Conectando o GND com jumper preto

Ligue o **pino GND** do ESP32 à linha negativa (azul) da protoboard usando um jumper preto.

![03 - Jumper preto (GND)](images/03.jpeg)

---

## 4️⃣ Ligando o GPIO2 com jumper vermelho

Conecte o pino **D2 (GPIO2)** do ESP32 à outra linha da protoboard com um jumper vermelho.  
Esse pino será usado para controlar o LED.

![04 - Jumper vermelho (GPIO2)](images/04.jpeg)

---

## 5️⃣ Adicionando o resistor

Coloque um **resistor de 220Ω** conectando a linha do GND (azul) até uma linha onde o LED será ligado.  
O resistor protege o LED da corrente excessiva.

![05 - Resistor adicionado](images/05.jpeg)

---

## 6️⃣ Inserindo o LED (ainda não ligado)

Coloque o LED na protoboard:
- **Perna longa (ânodo)**: onde o pino GPIO2 está
- **Perna curta (cátodo)**: próxima ao resistor

Ainda não conecte os fios!

![06 - LED colocado, mas não ligado](images/06.jpeg)

---

## 7️⃣ LED conectado ao circuito

Agora conecte:
- Perna longa do LED ao jumper vermelho (GPIO2)
- Perna curta do LED ao resistor, que está no GND

Circuito completo!

![07 - LED conectado](images/07.jpeg)

---

## 8️⃣ Conectando o ESP32 ao computador

Use um cabo USB para ligar o ESP32 ao seu computador.  
Agora estamos prontos para subir o código!

![08 - USB conectado](images/08.jpeg)

---

## 9️⃣ Código para piscar o LED

Abra a **Arduino IDE**, cole o código abaixo e envie para a placa:

```cpp
#define LED 2  // GPIO2

void setup() {
  pinMode(LED, OUTPUT);  // Define o pino como saída
}

void loop() {
  digitalWrite(LED, HIGH);  // Liga o LED
  delay(1000);              // Espera 1 segundo
  digitalWrite(LED, LOW);   // Desliga o LED
  delay(1000);              // Espera 1 segundo
}
