


#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <stdbool.h>

#define MAXTAMANHO 50

struct cliente {
    char nome[MAXTAMANHO];
    char endereco[MAXTAMANHO];
    char telefone[MAXTAMANHO];
    int idade;
    double peso;
};

struct fila {
    struct cliente *vetor;
    int inicio;
    int final;
    int capacidade;
};

struct fila* criarFila(int capacidade) {

    struct fila *f = (struct fila*) malloc(sizeof(struct fila));

    if(f == NULL) {
        printf("Erro.\n");
        exit(1);
    }

    f->vetor = (struct cliente*) malloc(capacidade * sizeof(struct cliente));

    if(f->vetor == NULL) {
        printf("Erro ao alocar vetor.\n");
        exit(1);
    }

    f->capacidade = capacidade;
    f->inicio = 0;
    f->final = 0;

    return f;
}

bool filaVazia(struct fila *f) {
    if(f->inicio == f->final) {
        return true;
    }
    return false;
}

bool filaCheia(struct fila *f) {
    if ((f->final + 1) % f->capacidade == f->inicio) {
        return true;
    }
    return false;
}

void enfileirar(struct fila *f, struct cliente c) {

    if(filaCheia(f)) {
        printf("Fila cheia!\n");
        return;
    }

    f->vetor[f->final] = c;
    f->final = (f->final + 1) % f->capacidade;

    printf("Cliente enfileirado com sucesso!\n");
}

void desenfileirar(struct fila *f) {

    if(filaVazia(f)) {
        printf("Fila vazia!\n");
        return;
    }

    printf("Cliente removido: %s\n", f->vetor[f->inicio].nome);

    f->inicio = (f->inicio + 1) % f->capacidade;
}


void liberarFila(struct fila *f) {
    free(f->vetor);
    free(f);
    printf("Memoria liberada!\n");
}


int main() {

    int capacidade;
    int opcao;

    printf("Digite a capacidade da fila (>=2): ");
    scanf("%d", &capacidade);
    getchar();

    if(capacidade < 2) {
        printf("Capacidade invalida!\n");
        return 1;
    }

    struct fila *f = criarFila(capacidade);

    do {

        printf("MENU\n");
        printf("1 - Enfileirar\n");
        printf("2 - Desenfileirar\n");
        printf("3 - Liberar fila\n");
        printf("4 - Sair\n");

        scanf("%d", &opcao);
        getchar();

        switch(opcao) {

            case 1: {

                struct cliente c;

                printf("Nome: ");
                fgets(c.nome, MAXTAMANHO, stdin);

                printf("Endereco: ");
                fgets(c.endereco, MAXTAMANHO, stdin);

                printf("Telefone: ");
                fgets(c.telefone, MAXTAMANHO, stdin);

                printf("Idade: ");
                scanf("%d", &c.idade);

                printf("Peso: ");
                scanf("%lf", &c.peso);
                getchar();

                enfileirar(f, c);
                break;
            }

            case 2:
                desenfileirar(f);
                break;

            case 3:
                liberarFila(f);
                break;

            default:
                printf("Opcao invalida!\n");
        }

    } while(opcao != 4);

    return 0;
}


## Observações do código.

### -> acessa um campo de uma scruct quando você tem um ponteiro para ela.


### Nesse código, usamos % para fazer um grande ciclo. Sempre quando o mod do começo e final é = 0, a gente volta no inicio valendo 0 novamente, ou seja, é um vetor infinito, ele não vai acabar, ele vai voltar sempre a 0 quando for alocando e retirando os valores.



bool filaVazia(struct fila *f) {
    if(f->inicio == f->final) {
        return true;
    }
    return false;
}

bool filaCheia(struct fila *f) {
    if ((f->final + 1) % f->capacidade == f->inicio) {
        return true;
    }
    return false;
}

### Nessa parte do código, pense o seguinte: ela será vazia se o final for igual ao começo. Porque isso é correto? porque se a gente inserir 2 elementos, final = 2  e se a gente tirar os mesmos 2 elementos, o começo = 2 e a fila estará vazia. 

### Na função filaCheia, ela encherá quando o mod do final+1 e capacidade = início. Sempre pense assim: se o final + 1 elemento for igual ao início, ela estará cheia. 
### Exemplo: capacidade = 5, começo = 2, final = 1. Final + 1 % 5 = 2 que é exatamente igual ao começo.