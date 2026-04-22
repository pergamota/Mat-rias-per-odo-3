
### O problema de Monty Hall é baseado em um programa de TV chamado Let's Make a Deal, onde o participante precisa escolher entre portas para ganhar um prêmio.

A situação é a seguinte:

- Existem **3 portas**
- Atrás de uma delas há um **carro (prêmio)**
- Atrás das outras duas há **cabras (perda)**

O jogador:

1. Escolhe uma porta (sem abrir)
2. O apresentador (Monty Hall), que **sabe onde está o prêmio**, abre uma das outras portas, mostrando uma cabra
3. O jogador então pode:
    - **Manter sua escolha**
    - ou **Trocar de porta**
# Modelo:

### Espaço: 3 portas -> 1 prêmio, 2 perdas.

### Etapas: 

- O prêmio é colocado aleatoriamente (probabilidade igual para cada porta)
- O jogador escolhe uma porta
- O apresentador abre uma porta com cabra (ele **nunca abre a porta com o prêmio)
- O jogador decide trocar ou não.
  
  
  
# Simulação:

```
import random

  

def simular_monty_hall(n_simulacoes):

    vitorias_trocando = 0

    vitorias_nao_trocando = 0

  

    for _ in range(n_simulacoes):

  

        portas = [0, 1, 2]

  

        premio = random.choice(portas)

  

        escolha_jogador = random.choice(portas)

  

        portas_possiveis = [

            porta for porta in portas

            if porta != escolha_jogador and porta != premio

        ]

        porta_aberta = random.choice(portas_possiveis)

  

        portas_restantes = [

            porta for porta in portas

            if porta != escolha_jogador and porta != porta_aberta

        ]

        porta_troca = portas_restantes[0]

  

        if escolha_jogador == premio:

            vitorias_nao_trocando += 1

  

        if porta_troca == premio:

            vitorias_trocando += 1

  

    prob_nao_trocar = vitorias_nao_trocando / n_simulacoes

    prob_trocar = vitorias_trocando / n_simulacoes

  

    print(f"Simulações: {n_simulacoes}")

    print(f"Probabilidade de ganhar NÃO trocando: {prob_nao_trocar:.4f}")

    print(f"Probabilidade de ganhar TROCANDO: {prob_trocar:.4f}")

  

simular_monty_hall(10000)

```


# Resultados obtidos com 10000 simulações:

**Simulações: 10000**
**Probabilidade de ganhar NÃO trocando: 0.3356**
**Probabilidade de ganhar TROCANDO: 0.6644**


# Comparação entre a simulação e resultados analíticos: 

* Os resultados obtidos por simulação aproximam-se dos valores teóricos de 1/3 e 2/3, o que valida tanto o modelo probabilístico quanto a implementação computacional.
  
  
# Relação do problema com Inteligência Artificial:

* Meu tema escolhido para relacionar com o problema de Monty Hall é a inteligência artificial porque assim como o problema de Monty Hall que existem possibilidades depois de uma escolha, também existe essa possibilidade em agentes de inteligência artificial porque eles trabalham com uma estratégia de resposta, mantendo sua decisão ou decidindo mudar após o usuário fornecer novas informações. Um agente pode repetir várias vezes essa simulação e verificar que a estratégia de troca é mais vantajosa, bem como a simulação de Monty Hall.
  
  
# Conclusão breve

* Ao resolver o problema de Monty Hall eu observei que meu pensamento sobre o problema estava errado o tempo todo , eu imaginei que a probabilidade de ganhar mantendo a porta seria maior porque ele sempre mostra a porta aberta com a cabra, mas colocando em prática o modelo analítico, eu desenvolvi todas as possibilidades e concluí que a probabilidade de ganhar seguindo a estratégia da troca realmente é maior.
  
*  Considero de suma importância o trabalho nos desafiar com uma pesquisa sobre a relação do problema e outra área que engloba o curso porque pesquisei sobre um dos pontos estratégicos de um agente de IA, engajando meu conhecimento sobre a área.