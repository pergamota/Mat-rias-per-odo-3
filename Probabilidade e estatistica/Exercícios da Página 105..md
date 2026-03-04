## 1️⃣ Experimento da Urna

### Enunciado

Uma urna contém 2 bolas brancas (B) e 3 bolas vermelhas (V). Retira-se uma bola ao acaso:

- Se for **branca (B)** → lança-se uma moeda.
    
- Se for **vermelha (V)** → devolve-se à urna e retira-se outra.
    

O experimento termina apenas quando uma bola branca é encontrada.

---

### Análise

O experimento só termina quando encontra a primeira bola branca.

Antes disso, podem ocorrer 0, 1, 2, 3, ..., n bolas vermelhas.

Para cada bola branca encontrada, lança-se uma moeda com dois resultados possíveis:

- C = cara
    
- K = coroa
    

Logo, o espaço amostral é infinito.

---

### Notação

- V → bola vermelha
    
- B → bola branca
    
- C → cara
    
- K → coroa
    
- S → espaço amostral
    

---

### Espaço Amostral

S={(B,C),(B,K),(V,B,C),(V,B,K),(V,V,B,C),(V,V,B,K),…}  

---

## 2️⃣ Lançamento de Dado até sair 5

### Enunciado

Lança-se um dado até que a face 5 apareça pela primeira vez.

---

### Análise

O experimento termina no primeiro 5.

Antes do 5 podem aparecer apenas números diferentes de 5:

{1,2,3,4,6}\{1, 2, 3, 4, 6\}{1,2,3,4,6}  

O número de lançamentos é indefinido:

- Pode sair 5 na primeira jogada.
    
- Pode sair após 2, 3, 10 ou 1000 jogadas.
    

Logo, o espaço amostral é infinito enumerável.

---

### 📊 Espaço Amostral

S={(5),(x1,5),(x1,x2,5),(x1,x2,x3,5),… }

---

## 3️⃣ Torneio entre A, B e C

### Enunciado

- A joga contra B.
    
- O vencedor joga contra C.
    
- O torneio termina quando:
    
    - alguém ganha duas partidas consecutivas, **ou**
        
    - são disputadas 4 partidas no total.
        

---

### Análise do caso inicial: A vence B

1️⃣ Jogo 1: A vence B  
Sequência: (A)

2️⃣ Jogo 2: A vs C

- Se A vence → (A, A) → A campeão.
    
- Se C vence → sequência: (A, C)
    

3️⃣ Jogo 3: C vs B

- Se C vence → (A, C, C) → C campeão.
    
- Se B vence → sequência: (A, C, B)
    

4️⃣ Jogo 4: B vs A

- Se B vence → (A, C, B, B) → B campeão.
    
- Se A vence → (A, C, B, A)
    

Mesmo sem duas vitórias consecutivas, o torneio termina porque atingiu 4 partidas.

---

### Observação Importante

O torneio sempre termina:

- quando alguém vence duas seguidas
    
- ou obrigatoriamente na quarta partida
    

Logo, o espaço amostral é finito.