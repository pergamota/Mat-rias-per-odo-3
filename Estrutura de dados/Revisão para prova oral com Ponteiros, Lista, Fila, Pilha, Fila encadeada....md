
# Porque usar ponteiros:

Usa-se ponteiro quando é necessário acessar ou modificar a memória original ou quando há alocação dinâmica com malloc. Caso contrário, pode-se usar variável normal.
Essa modificação acontece porque o ponteiro guarda o endereço de uma variável e tem acesso para modificar.


# O QUE É UM NÓ

## DEFINIÇÃO

Nó = dado + ponteiro para o próximo

## EXEMPLO

typedef struct No {  
    Cliente *it;  
    struct No *prox;  
} No;

## FUNÇÃO DO NÓ

👉 permitir ligação entre elementos

## POR QUE NÃO USAR SÓ O DADO?

Cliente não aponta para outro Cliente

👉 precisa do nó

---

# 1. MONTAR E DESMONTAR NÓ

## montarNo

No* montarNo(Cliente *c)

👉 cria nó  
👉 coloca dado  
👉 prox = NULL

## pensamento

criar caixa com dado + ligação

## desmontarNo

Cliente* desmontarNo(No *n)

👉 pega dado  
👉 libera nó  
👉 retorna dado

## IMPORTANTE

não libera o dado aqui

---

# 2. LISTAS ENCADEADAS

## ESTRUTURA

typedef struct {  
    No *primeiro;  
} Lista;

## INSERÇÃO

novo → primeiro  
primeiro → novo

## REMOÇÃO

anterior → próximo do atual

## VARIÁVEIS IMPORTANTES

|Nome|Função|
|---|---|
|`aux`|percorre|
|`ant`|guarda anterior|

## FRASE

remover = fazer o anterior pular o atual

---

# 3. FILAS (QUEUE)

## CONCEITO

FIFO → primeiro entra, primeiro sai

## ESTRUTURA

No *inicio;  
No *final;

## ENFILEIRAR

final → novo  
final = novo

## DESENFILEIRAR

inicio = inicio->prox

## CASO ESPECIAL

se ficar vazia → inicio = NULL e final = NULL

---

# 4. FILA COM VETOR

## DIFERENÇA

usa índice ao invés de ponteiro

## LINHA IMPORTANTE

(f->final + 1) % capacidade

## SIGNIFICADO

faz a fila voltar para o início (circular)

---

# 5. LISTA DUPLAMENTE ENCADEADA

## ESTRUTURA

struct No {  
    prox;  
    ant;  
}

## DIFERENÇA

anda para frente e para trás

## IMPORTANTE

precisa atualizar 4 ponteiros

---

# 6. CONCEITOS DAS QUESTÕES (NÍVEL PROVA)

## 1. Ponteiro na função

Lista *l

* permite alterar estrutura original

---

## 2. Ponteiro dentro do nó

Cliente *it

* evita cópia  
* economiza memória

---

## 3. Ordem da inserção na fila

final->prox = novo;  
final = novo;

* não pode inverter

---

## 4. Remoção com `ant == NULL`

* significa remover o primeiro

---

## 5. Ordem do while

aux != NULL && ...

* evita acessar NULL

---

## 6. Uso do %

* transforma fila em circular

---

## 7. Free no nó

* não liberar dado ainda

---

## 8. Lista dupla

* precisa manter consistência dos dois lados

---

## 9. Verificação de fila vazia

* garantir integridade

---

## 10. Dois frees

free(dado);  
free(no);

* evita memory leak