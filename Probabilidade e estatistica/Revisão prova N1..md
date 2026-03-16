
# Mapa de estudo da lista – Introdução à Probabilidade

## Bloco 1 — Fundamentos da probabilidade

Conceitos:

- espaço amostral
    
- evento
    
- cálculo básico de probabilidade
    

Fórmula principal:

probabilidade de um evento = número de casos favoráveis dividido pelo número total de casos possíveis


O que normalmente acontece nessas questões:

- contar possibilidades
    
- calcular proporções
    
- trabalhar com escolha de elementos
    

---

# Bloco 2 — Probabilidade com reposição e sem reposição

Conceitos:

- experimento com reposição
    
- experimento sem reposição
    

Diferença importante:

com reposição  
→ as probabilidades **não mudam**

sem reposição  
→ as probabilidades **mudam a cada retirada**

Raciocínio típico:

primeiro evento × segundo evento

---

# Bloco 3 — Eventos independentes

Conceito:

dois eventos são independentes quando **um não altera a probabilidade do outro**.

Regra:

probabilidade de A e B = probabilidade de A × probabilidade de B

Aplicações típicas:

- falhas de equipamentos
    
- erros em bits
    
- alarmes
    
- componentes funcionando
    

---

# Bloco 4 — Probabilidade do complemento

Conceito muito usado em provas.

Ideia:

é mais fácil calcular **o contrário do que queremos**.

Fórmula:

probabilidade de A = 1 menos probabilidade de não A

Exemplo clássico:

probabilidade de **pelo menos um funcionar**

---

# Bloco 5 — Sistemas de confiabilidade

Muito comum em engenharia.

## Sistema em série

todos os componentes precisam funcionar.

Regra:

multiplicamos as probabilidades.

exemplo:

equipamento A × equipamento B × equipamento C

---

## Sistema em paralelo

basta **um componente funcionar**.

Regra mais usada:

probabilidade de funcionamento =  
1 menos probabilidade de todos falharem.

---

# Bloco 6 — Probabilidade condicional

Conceito:

probabilidade de um evento **sabendo que outro aconteceu**.

Notação:

P(A | B)

Significado:

probabilidade de A **sabendo que B aconteceu**.

---

# Bloco 7 — Probabilidade total

Quando um evento pode acontecer **por vários caminhos diferentes**.

Regra:

somar probabilidades dos caminhos possíveis.

Estrutura típica:

evento pode ocorrer por:

caminho 1  
caminho 2  
caminho 3

Então:

probabilidade total = soma de todos os caminhos.

---

# Bloco 8 — Teorema de Bayes

Usado quando queremos **descobrir a causa de algo que aconteceu**.

Ideia:

sabemos o resultado  
queremos descobrir **qual foi a origem mais provável**.

Exemplo clássico:

uma máquina produziu uma peça defeituosa  
queremos saber qual máquina provavelmente produziu.


# Questões da Lista.


# 1 - O que significa “no máximo um problema”

“No máximo um” significa:

- nenhum problema  
    
     ou
    
- exatamente um problema

Então precisamos calcular:

probabilidade de **zero problemas**  
mais  
probabilidade de **exatamente um problema**

---

# Probabilidade de nenhum problema

Se cada problema tem 5% de chance de ocorrer, então a chance de **não ocorrer** é:

95%

ou em decimal:

0.95

Como existem **quatro possíveis problemas**, e eles são **independentes**, multiplicamos as probabilidades.

Então:

probabilidade de nenhum problema =

0.95 × 0.95 × 0.95 × 0.95

resultado:

0.81450625

Ou seja:

aproximadamente **81,45%**

---

# Probabilidade de exatamente um problema

Agora queremos o caso onde **apenas um problema acontece**.

Existem quatro possibilidades:

1. queda de energia acontece e os outros três não
    
2. falha do equipamento acontece e os outros três não
    
3. erro de leitura acontece e os outros três não
    
4. erro de digitação acontece e os outros três não
    

---

## Probabilidade de um caso específico

Exemplo:

queda de energia acontece:

0.05

os outros três não acontecem:

0.95 × 0.95 × 0.95

Então:

0.05 × 0.95 × 0.95 × 0.95

resultado:

0.04286875

---

## Como existem quatro casos iguais

Multiplicamos por quatro:

4 × 0.04286875

resultado:

0.171475

ou aproximadamente:

**17,15%**

---

# Agora somamos os dois resultados

Lembre:

no máximo um problema =

nenhum problema  
mais  
exatamente um problema

Então:

0.81450625  
mais  
0.171475

resultado:

0.98598125

---

# Resultado final

A probabilidade de um dado ser coletado com **no máximo um problema** é aproximadamente:

**0.986**

ou

**98,6%**

---

# 2 - Dados do problema

Probabilidade de uma pessoa **ter a doença**:

15%

Em decimal:

0.15

Então a probabilidade de **não ter a doença** é:

0.85

---

### Laboratório A

- positivo para **80% dos doentes**
    
- positivo para **10% dos saudáveis**
    

Ou seja:

P(positivo A | doente) = 0.80  
P(positivo A | saudável) = 0.10

---

### Laboratório B

- positivo para **70% dos doentes**
    
- positivo para **5% dos saudáveis**
    

Ou seja:

P(positivo B | doente) = 0.70  
P(positivo B | saudável) = 0.05

---

### Informação importante

O problema diz que **os resultados dos laboratórios são independentes**.

Isso significa que podemos **multiplicar as probabilidades**.

---

# O que a questão pede

Queremos a probabilidade de:

**uma pessoa obter resultado positivo nos dois laboratórios**

Ou seja:

positivo em A **E** positivo em B.

---

# Existem dois cenários possíveis

Uma pessoa pode ser:

1️⃣ doente  
2️⃣ saudável

Então calculamos os dois casos e depois somamos.

---

# Caso 1 — pessoa doente

Probabilidade da pessoa ser doente:

0.15

Probabilidade de:

positivo em A = 0.80  
positivo em B = 0.70

Como os testes são independentes:

probabilidade de positivo nos dois:

0.80 × 0.70 = 0.56

Agora multiplicamos pela chance da pessoa ser doente:

0.15 × 0.56 = 0.084

---

# Caso 2 — pessoa saudável

Probabilidade de ser saudável:

0.85

Probabilidade de erro nos testes:

positivo em A = 0.10  
positivo em B = 0.05

Como são independentes:

0.10 × 0.05 = 0.005

Agora multiplicamos:

0.85 × 0.005 = 0.00425

---

# Probabilidade total

Agora somamos os dois caminhos:

0.084 + 0.00425

Resultado:

0.08825

---

# Resultado final

Probabilidade de uma pessoa qualquer obter **positivo nos dois exames**:

0.08825

ou aproximadamente:

**8.83%**

---

# 3 - Informações do problema

Tipos de rocha:

LF (levemente fissurada)  
probabilidade = 0,8

MF (moderadamente fissurada)  
probabilidade = 0,1

F (fortemente fissurada)  
probabilidade = 0,1

---

## Confiabilidade do projeto para cada tipo

Se a rocha for **LF**

probabilidade de **não falhar** = 0,95

logo

probabilidade de **falhar** = 0,05

---

Se a rocha for **MF**

o problema diz que a falha **dobra**.

então:

probabilidade de falha = 2 × 0,05 = 0,10

logo

probabilidade de não falhar = 0,90

---

Se a rocha for **F**

a falha é **10 vezes maior que na LF**

então:

probabilidade de falha = 10 × 0,05 = 0,50

logo

probabilidade de não falhar = 0,50

---

# Tabela organizada

|Tipo|Probabilidade|Não falhar|Falhar|
|---|---|---|---|
|LF|0,8|0,95|0,05|
|MF|0,1|0,90|0,10|
|F|0,1|0,50|0,50|

---

# Parte (a)

Probabilidade de **o túnel não falhar**

Usamos **probabilidade total**.

multiplicamos cada cenário e somamos.

---

### Caso 1 — rocha LF

0,8 × 0,95 = 0,76

---

### Caso 2 — rocha MF

0,1 × 0,90 = 0,09

---

### Caso 3 — rocha F

0,1 × 0,50 = 0,05

---

### Somando

0,76 + 0,09 + 0,05 =

0,90

---

**Resposta da letra (a)**

probabilidade de o túnel **não falhar**

= **0,90**

ou

**90%**

---

# Parte (b)

Agora a pergunta muda.

Se o túnel **falhou**, qual a probabilidade da rocha ser **LF**?

Agora usamos **Teorema de Bayes**.

Queremos:

probabilidade de LF **sabendo que houve falha**

---

# Primeiro calculamos a probabilidade de falha total

Falha pode acontecer em três cenários.

---

### Caso LF

0,8 × 0,05 = 0,04

---

### Caso MF

0,1 × 0,10 = 0,01

---

### Caso F

0,1 × 0,50 = 0,05

---

Somando:

0,04 + 0,01 + 0,05 =

0,10

---

# Aplicando Bayes

probabilidade de LF dado que houve falha =

probabilidade de (LF e falha)  
dividido por  
probabilidade total de falha

---

probabilidade de (LF e falha)

0,8 × 0,05 = 0,04

---

Então:

0,04 / 0,10

resultado:

0,4



# 4 - Informações do problema

Proporção de galões de cada fornecedor:

Fornecedor A → 40% → 0,40  
Fornecedor B → 30% → 0,30  
Fornecedor C → 20% → 0,20  
Fornecedor D → 10% → 0,10

---

Probabilidade de **efeito corrosivo** em cada fornecedor:

A → 5% → 0,05  
B → 5% → 0,05  
C → 3% → 0,03  
D → 3% → 0,03

---

# 2. Árvore de probabilidades

Início  
│  
├─ A (0,40)  
│   ├─ Corrosivo (0,05)  → 0,40 × 0,05 = 0,02  
│   └─ Não corrosivo (0,95)  
│  
├─ B (0,30)  
│   ├─ Corrosivo (0,05)  → 0,30 × 0,05 = 0,015  
│   └─ Não corrosivo (0,95)  
│  
├─ C (0,20)  
│   ├─ Corrosivo (0,03)  → 0,20 × 0,03 = 0,006  
│   └─ Não corrosivo (0,97)  
│  
└─ D (0,10)  
    ├─ Corrosivo (0,03)  → 0,10 × 0,03 = 0,003  
    └─ Não corrosivo (0,97)

---

# Letra (a)

Probabilidade de o galão **ser corrosivo**.

Somamos todos os caminhos corrosivos.

0,02

- 0,015
    
- 0,006
    
- 0,003
    

Resultado:

0,044

---

 **Resposta da letra (a)**

probabilidade do galão ser corrosivo:

0,044

ou

**4,4%**

---

# Letra (b)

Agora queremos:

probabilidade de o galão ser do **fornecedor A dado que é corrosivo**.

Usamos **Teorema de Bayes**.

---

## Probabilidade de A e corrosivo

0,40 × 0,05 = 0,02

---

## Probabilidade total de corrosivo

já calculamos:

0,044

---

## Aplicando Bayes

probabilidade de A dado corrosivo:

0,02 / 0,044

Resultado:

0,4545

---

# Resultado final

probabilidade do galão ser do fornecedor A:

aproximadamente

**0,4545**

ou

**45,45%**