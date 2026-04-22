
# Ponteiro: variável que guarda um endereço de memória.

* Declaração de ponteiro: use o tipo da variável e depois use asterisco juntamente com o nome do ponteiro.


### Free(): libera a memoria reservada alocada dinamicamente.

---
# BASE: PONTEIROS

---

## O QUE É UM PONTEIRO

 * Variável que guarda **endereço de memória**

int x = 10;  
int *p = &x;

---

## PRINCIPAIS OPERADORES

|Símbolo|Significado|
|---|---|
|`*`|acessa o valor apontado|
|`&`|pega o endereço|
|`**`|ponteiro para ponteiro|

---

## EXEMPLO COMPLETO

int x = 10;  
int *p = &x;

x  → 10  
p  → endereço de x  
*p → 10  
&p → endereço de p

---

## FRASE PRA PROVA

Ponteiro guarda endereço, * acessa valor, & obtém endereço

---

# 2. DIFERENÇA ENTRE `*` E `**`

---

## `*` (ponteiro simples)

int * p;

👉 aponta para um valor

---

## `**` (ponteiro duplo)

int ** p;

👉 aponta para outro ponteiro

---

## QUANDO USAR

|Situação|Usar|
|---|---|
|alterar valor|`*`|
|alterar ponteiro original|`**`|

---
## EXEMPLO REAL (LISTA)

void inserir(No **lista)

👉 precisa alterar o início da lista

---

## ERRO COMUM

usar * quando precisava de **

👉 resultado: lista não muda