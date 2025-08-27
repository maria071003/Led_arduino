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

##  ESP32 encaixado na protoboard

Insira o ESP32 no centro da protoboard, com espaço livre nas laterais para conectar os fios e componentes.

![02 - ESP32 encaixado](![2 img](https://github.com/user-attachments/assets/f7d46853-183e-42b3-8aa7-65a12c6bf3a9)
)

---

##  Conectando o GND com jumper preto

Ligue o **pino GND** do ESP32 à linha negativa (azul) da protoboard usando um jumper preto.

![03 - Jumper preto (GND)](![3 img](https://github.com/user-attachments/assets/80a5eaa2-95e0-4b83-8bf6-a5481b353f7c)
)

---

##  Ligando o GPIO2 com jumper vermelho

Conecte o pino **D2 (GPIO2)** do ESP32 à outra linha da protoboard com um jumper vermelho.  
Esse pino será usado para controlar o LED.

![04 - Jumper vermelho (GPIO2)](![4 img](https://github.com/user-attachments/assets/1fad64cd-9d4d-4032-ad31-babd29c4fffe)
)

---

##  Adicionando o resistor

Coloque um **resistor de 220Ω** conectando a linha do GND (azul) até uma linha onde o LED será ligado.  
O resistor protege o LED da corrente excessiva.

![05 - Resistor adicionado](![5 img](https://github.com/user-attachments/assets/e5f457f9-fabc-46fd-ade6-85f6d7320d88)
)

---

## Inserindo o LED (ainda não ligado)

Coloque o LED na protoboard:
- **Perna longa (ânodo)**: onde o pino GPIO2 está
- **Perna curta (cátodo)**: próxima ao resistor

Ainda não conecte os fios!

![06 - LED colocado, mas não ligado](![6 img](https://github.com/user-attachments/assets/9c6b0a26-6adf-4fb7-a883-2ed2e7a98e49)
)

---

## LED conectado ao circuito

Agora conecte:
- Perna longa do LED ao jumper vermelho (GPIO2)
- Perna curta do LED ao resistor, que está no GND

Circuito completo!

![07 - LED conectado](![7 img](https://github.com/user-attachments/assets/a38d7c4d-ecd0-4310-89fd-a0c630d05b2f)
)

---

## Conectando o ESP32 ao computador

Use um cabo USB para ligar o ESP32 ao seu computador.  
Agora estamos prontos para subir o código!

![08 - USB conectado](![8 img](https://github.com/user-attachments/assets/d2a67b7e-d986-4bc2-bf9e-aecd173b2689)
)

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


