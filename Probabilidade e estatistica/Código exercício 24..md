```
#include <stdio.h>  
  
int main() {  
double p, q;  
  
scanf("%lf %lf", &p, &q);  
  
p = p / 100.0;  
q = q / 100.0;  
  
double result = (p*p + q*q) / (p + q);  
  
printf("%.12f\n", result);  
  
return 0;  
}
```

# Problema das duas moedas

Temos duas moedas:

Moeda A → probabilidade de dar cara = p/100  
Moeda B → probabilidade de dar cara = q/100

A pessoa escolhe uma moeda **aleatoriamente**.

Então:

probabilidade de escolher A = 0.5  
probabilidade de escolher B = 0.5

Depois a moeda é lançada duas vezes.

Sabemos que **o primeiro lançamento deu cara**.

Queremos descobrir:

qual é a probabilidade do **segundo lançamento também dar cara**.

---

# Caminhos possíveis

Existem dois caminhos possíveis para acontecer **cara duas vezes**.

Caminho 1:

escolher moeda A  
dar cara  
dar cara

probabilidade:

0.5 × (p/100) × (p/100)

---

Caminho 2:

escolher moeda B  
dar cara  
dar cara

probabilidade:

0.5 × (q/100) × (q/100)

---

Como os dois caminhos são **mutuamente exclusivos**, podemos somar as probabilidades.

Probabilidade de duas caras seguidas:

(0.5 × p/100 × p/100) + (0.5 × q/100 × q/100)

---

# Probabilidade do primeiro lançamento ser cara

Também existem dois caminhos:

escolher A e dar cara

0.5 × (p/100)

ou

escolher B e dar cara

0.5 × (q/100)

Somando:

(0.5 × p/100) + (0.5 × q/100)

---

# Probabilidade condicional

### O que muda na probabilidade condicional

Probabilidade condicional aparece quando **nós já sabemos que alguma coisa aconteceu**.

Ou seja:

estamos calculando uma probabilidade **com uma informação extra**.

Essa informação **muda o espaço de possibilidades**.

# A ideia central

Probabilidade condicional significa:

recalcular a probabilidade considerando apenas os casos que ainda são possíveis.

### Questão.

A fórmula usada é:

probabilidade do segundo lançamento dar cara sabendo que o primeiro foi cara

=

probabilidade de duas caras seguidas

dividido pela

probabilidade do primeiro lançamento ser cara

---

Substituindo pelos valores:

((0.5 × p/100 × p/100) + (0.5 × q/100 × q/100))  
dividido por  
((0.5 × p/100) + (0.5 × q/100))

---

# Simplificação

Primeiro podemos cortar o fator **0.5** que aparece em cima e embaixo.

Fica:

((p/100 × p/100) + (q/100 × q/100))  
dividido por  
((p/100) + (q/100))

---

Agora multiplicando:

p/100 × p/100 = p² / 100²  
q/100 × q/100 = q² / 100²

Então:

((p² / 100²) + (q² / 100²))  
dividido por  
((p/100) + (q/100))

---

Agora cortamos o fator **100** que aparece em cima e embaixo.

Resultado final:

(p² + q²) / (p + q)

---

# Resultado final

A probabilidade do segundo lançamento dar cara sabendo que o primeiro foi cara é:

(p² + q²) / (p + q)