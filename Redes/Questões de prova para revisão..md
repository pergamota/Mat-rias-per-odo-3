### PROVA 01/02

# QUESTÃO 1. 
Tempo de transmissão: diretamente proporcional ao tamanho do quadro e inversamente proporcional à taxa de transmissão.

# QUESTÃO 2.

Existem 2 formas de calcular SNR, tudo vai depender de como são os dados da questão.

### 1 forma : se for Potência (W, mW, μW) usamos:

### SNR = S/N 

* S = potência do sinal
- N = potência do ruído


Mas lembre-se, o calculo precisa estar na mesma unidade de medida, logo, siga as instruções: 

W = 10 elevado a 0.
mW = 10 elevado a - 3.
μW = 10 elevado a - 6.


Exemplo de questão: 

### 📌 Enunciado

Um canal possui largura de banda de **4000 Hz**. A potência do sinal é **5 mW** e a potência do ruído é **0,05 mW**.

Calcule:

1. SNR
    
2. SNR em dB
    

---

## ✅ 1) SNR

SNR = S/N 

SNR = 5/0,05

SNR = 100.

✔ **SNR = 100 (sem unidade)**

---

## ✅ 2) SNR em dB

SNRdb = 10 log (100)

SNRdb = 10 x 2 = 20 dB

✔ **SNR = 20 dB**


### 2 forma : se for Tensão (V, mV) 

### SNR = (Vs/Vn) elevado a 2.

- *Vs* ​ = tensão do sinal
- *Vn* ​ = tensão do ruído
  
### 📌 Enunciado

Um canal de voz possui largura de banda de **4 kHz**. O sinal possui amplitude de **8 V** e o ruído de **2 mV**.

Calcule:

1. SNR 
2. SNR em DB
## ⚠️ 1) Converter unidades

2mV = 0,002 V

---

## ✅ 2) SNR (com tensão)

SNR = (Vs/Vn) elevado a 2.

SNR = (8/0,002) elevado a 2.

SNR = (4000) elevado a 2.

SNR = 16.000.000


✔ **SNR = 16.000.000 (sem unidade)**


### ✅ 3) SNR em DB

SNRdb = 10 log (16.000.000) é aproximadamente 7,2 
 
SNRdb = 10 x 7,2 

SNRdb = 72 aproximadamente



# QUESTÃO 3.

### Cite 1 exemplo de rede Simplex, Half-duplex, Full-duplex:

- **Simplex:** comunicação em um único sentido (ex: televisão)
    
- **Half-duplex:** comunicação nos dois sentidos, mas não ao mesmo tempo (ex: dispositivos blueetoth)
    
- **Full-duplex:** comunicação nos dois sentidos ao mesmo tempo (ex: telefone)



# Questão 4.

### O PDU de transporte  = cabeçalho da camada ... + PDU da camada ... (COMPLETE A FRASE).


Resposta: O PDU de transporte recebe a camada de transporte + PDU da camada de rede.



# Questão 5.
### O endereço MAC é um endereço do tipo ... e é inserido no cabeçalho da camada de ... (COMPLETE A FRASE).


Resposta: O endereço MAC é um endereço do tipo físico e é enserido no cabeçalho da camada de enlace de dados.



# Questão 6.

### Um roteador wi-fi foi configurado para operar no canal 1, cuja frequência varia de 2401 a 2423 MHz. Qual a largura de banda desse canal?

Fórmula:

B = Fmax - Fmin 

B = 2423 - 2401 

B = 22 MHz


### Questão 7.

### Um sinal é composto por 3 ondas senoidais: 1 com frequencia de 10 Hz e amplitude = 9, 2 com frequência de 30 Hz e amplitude = 3, 3 com frequência de 90 Hz e amplitude = 1.



# QUESTÃO 8.

### Um sinal digital possui 16 níveis de voltagem. Quantos bits serão transportados em cada nível ?

fórmula: 

bits = log base 2 (L)

bits = log base 2 (16)

como log está na base 2, pense assim: qual número elevado na base 2 = 16?

log 2 (16) = 4 bits



# QUESTÃO 9.

### Um sinal digital que usa 8 níveis de voltagem é transmitido em um canal passa-baixa cuja maior frequência tem período = 20 ms. Qual a taxa de dados máxima em bps que pode ser transmitida nesse canal, supondo um canal sem ruído?


Dados:

- L = 8 níveis
    
- período = 20 ms
    

---

### 1️⃣ Converter período

T = 20 ms 
T = 0,02 s

(Dividimos por 1000 porque um é 10 elevado a -3 e o outro é 10 elevado a 0)

---

### 2️⃣ Frequência

f = 1/T 

f = 1/0,02

f = 50 Hz

---

### 3️⃣ Nyquist

C = 2B Log base 2 (L)

C = 2 x 50 x Log base 2 (8) 

C = 2 x 50 x 3 

C = 300 bps

✔ **Resposta final: 300 bps**




# PROVA 01/01


# QUESTÃO 1:

### CITE DOIS FATORES QUE DETERMINAM UM SISTEMA DE COMUNICAÇÃO É LAN OU WAN.

Lan é uma rede privada e atende apenas uma casa, um escritório... 
Wan é uma rede pública ou alugada que conecta, por exemplo, 2 escritórios em cidades diferentes.


# QUESTÃO 2:

### AS 4 CAMADAS DO MODELO TCP/IP SÃO:

Aplicação, transporte, internet, acesso à rede.



# QUESTÃO 3:

### CITE DIFERENÇAS ENTRE UM CANAL PASSA-BAIXA E UM CANAL PASSA-FAIXA.

Passa-baixa: permite que sinais com frequências muito baixas passem sem problemas, começando na frequência 0.

Passa-faixa: ignora as frequências muito baixas e muito altas, focando apenas no meio.


# QUESTÃO 4:

### Qual a taxa de transferência em bps de um sinal no qual 10 bits duram 20 us?

Fórmula:

Taxa = bits/tempo

* Como o tempo precisar estar em segundos, sabemos que us é 10 elevado a -6, logo, 20 us = 0,00002.

Taxa = 10/0,00002 

Taxa = 500000 bps


# QUESTÃO 5:

### A atenuação de um sinal é -10 db. Qual é a potência final do sinal em W e dBm se inicialmente ele tinha 5W?

dB = 10 log base 10 (Pf/Pi)

-10 = 10 log base 10 (Pf/5)

-1 = log (Pf/5)

 log -1 = 10 elevado -1
 
 10 elevado a -1 = (Pf/5)
 
 0,1 =  (Pf/5)
 
 dB = 0.5 W ✅
 
 
 dBm = 10 log (P/1mW)
 
 Precisamos fazer a conversão!
 
 1 W = 1000 mW --> 0.5 w = 500mW.
 
 dBm = 10 log (500) aproximadamente 2.7
 
 dBm = 10 x 2,7 
 
 dBm = 27 dBm. ✅
 
 
# Questão 6:

### Se a voltagem máxima de um sinal for 20x a voltagem máxima do ruído, qual é sua SNR? qual a sua SNRdb?

SNR = (Vs/Vn) elevado a 2

SNR = 20 elevado a 2 = 400.

SNR = 400. ✅


SNRdb = 10 log (400)

log 400 aproximadamente 2.6

SNRdb = 10 x 2.6

SNRdb = 26 dB ✅



# PROVA 01-03

# Questão 1: 
### A figura a seguir mostra a saída do comando netstat em um computador Windows.

### a) Qual o endereço lógico externo da primeira conexão? 
 É a primeira linha de números da tabela ENDEREÇO EXTERNO. 
### b) Qual o endereço lógico local dessas 4 conexões?
São todas as linhas da tabela ENDEREÇO LOCAL.
### c) Qual o protocolo de aplicação dessas 4 conexões?
É o protocolo HTTP/HTTPS.
### d) Qual o protocolo de transporte dessas 4 conexões?
Fica na tabela PROTO (TCP).


# QUESTÃO 2:

### Qual a causa do atraso de enfileiramento em uma rede de computadores?

O atraso de enfileiramento ocorre quando os pacotes chegam ao roteador mais rapidamente do que podem ser transmitidos, causando formação de filas devido à **congestão da rede**.


# QUESTÃO 3:

### Por que a transmissão de bits em banda base não pode usar um canal passa faixa?

A transmissão pelo canal passa faixa não pode ser usada pela transmissão de bits porque passa faixa não consegue captar frequências perto de 0, ou seja, ela impossibilitaria a transmissão correta do sinal.
