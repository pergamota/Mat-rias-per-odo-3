
## Problema

Um caminhante começa no ponto **0**.

A cada passo ele pode:

- ir **+1** (direita) com probabilidade de 50% ou 1/2.
    
- ir **−1** (esquerda) com probabilidade de 50% ou 1/2.
    

👉 Queremos saber:

## ✔ Qual a probabilidade dele voltar ao ponto inicial após **4 passos**?


# 🧠 PASSO 1: Entender o que precisa acontecer

✔ O que precisamos entender: para voltar ao ponto inicial a quantidade de passos para a direita precisa ser exatamente igual aos passos para a esquerda. 

### Como temos 4 passos no nosso exemplo, a única forma é 2 para direita e 2 para esquerda.

---

# 🧠 Passo 2: Usar combinação:

Como sabemos que a mesma quantidade de passos precisam ser iguais para cada lado, buscaremos o lado direito. Como temos 4 posições possíveis, precisamos escolher 2 posições onde ficarão os lados direito, logo, isso torna uma combinação de 4/2 = (4/2).

### Fórmula da combinação: (n/k) = n! / k! (n - k)!

### O que significa:

- n = total de posições → 4
    
- k = quantas queremos escolher → 2
    
- n − k = posições restantes → 2
  

### Calculando:

### 👉 n! = 4! ( 4 * 3 * 2 * 1 = 24).
### 👉 k! = 2! (2 * 1 = 2).
### 👉 (n - k)! = 2! = 2.
### 👉 (n / k) = 24 / 2 * 2  = 24/4 = 6.


Logo, 6 possibilidades entre X caminhos possíveis.

---

# 🧠 Passo 3: O que os 6 caminhos representam?

Eles representam:

✔ todas as sequências que fazem o caminhante voltar ao zero.

Mas existem outras sequências que NÃO voltam.

Logo, precisamos comparar:

### Caminhos favoráveis x caminhos possíveis.

---

# 🧠 Passo 4: Quantos caminhos possíveis existem?

Cada passo tem 2 opções:

➡ direita  
⬅ esquerda

Para 4 passos:

2 * 2 * 2 * 2  = 2 Elevado a 4, logo = 16.

👉 existem **16 caminhos possíveis**.

---

# 🧠 Passo 5: Por que cada caminho tem a mesma probabilidade?

Cada passo tem probabilidade:

* 1/2 ou 50%

Para um caminho específico, multiplicamos:

exemplo: ➡⬅➡⬅

1/2 * 1/2 * 1/2 * 1/2 = (1/2) elevado a 4 = 1/16.

👉 cada sequência tem probabilidade **1/16**.

---

# 🧠 PASSO 6: Usando os 6 caminhos

Sabemos que:

- existem 6 caminhos que retornam ao zero.
    
- cada um tem probabilidade 1/16.
    

Então somamos:

### P = 6 * 1/16 = 6/16, Logo, podemos dividir por 2 em cima e em baixo, P = 3/8 = 0.375 

# ✅ RESULTADO FINAL:

### 37,5%.