
# Funções básicas do computador (MUITO COBRADO)

Um computador sempre faz 4 coisas:

1. **Processamento** → calcula e resolve coisas (CPU)
2. **Armazenamento** → guarda dados (Memória)
3. **Transferência (entrada/saída)** → recebe e envia dados
4. **Controle** → coordena tudo (UC)
   
   
## Detalhamento da IAS:

* AC: acumulador.
* MQ: usado em multiplicação/divisão.
* MBR: guarda dados vindo da memória.
* MAR: guarda endereço vindo da memória.
* IR: instrução atual.
* IBR: segunda instrução.
* PC: próxima instrução.
  
  
## Ciclo de Von Neuman: 

* Busca, decodifica, executa.
  
  
## Gargalo de Von Neumann: 

* **O gargalo de Von Neumann** é a limitação causada pelo fato de **dados e instruções usarem o mesmo caminho entre a memória e a CPU**, o que reduz a velocidade do sistema.**


## CISC: 

* **É um conjunto de instruções moderna que possui instruções complexas, executando instruções grandes, mas deixando a execução mais lenta.
  
## RISC:

* **É um conjunto de instruções moderna que possui instruções simples, sendo mais rápida e mais eficiente. 
  
  

## Barramentos:

* **Barramentos** são os “caminhos” que transportam informações dentro do computador.

Eles conectam:
- CPU
- Memória
- Dispositivos de entrada e saída (I/O)

Sem barramento, as partes do computador não conseguem se comunicar.


## Linhas de barramento (ideia importante!)

Cada barramento é formado por várias **linhas** (fios).

Quanto mais linhas → mais informação pode ser enviada ao mesmo tempo.

Exemplo:

- 8 linhas → envia 8 bits por vez
- 32 linhas → envia 32 bits por vez (mais rápido)


# Funcionamento simples (passo a passo)

Exemplo: CPU quer somar um valor

1. CPU usa **barramento de endereço** → diz onde está o dado.
2. CPU usa **barramento de controle** → manda “LER”.
3. Memória envia o dado pelo **barramento de dados**.
4. CPU processa (ULA).
5. Resultado pode voltar para memória.
   

   
# Arquitetura de Voumann: 

## Principal característica: 
* **Armazenamento conjunto de dados e instruções na mesma memória**
  
### Explicação clara do modelo de Voumann: 

* **O modelo de Von Neumann é uma arquitetura de computadores em que dados e instruções são armazenados na mesma memória principal. Ele é composto por memória, CPU (formada pela unidade de controle, unidade lógica e aritmética e registradores (ULA)) e dispositivos de entrada e saída. A unidade de controle busca e decodifica instruções, enquanto a ULA executa operações, caracterizando um sistema de propósito geral.**
  
  
## 1. Descreva as funções básicas de um computador e explique o papel de cada uma.

* **As funções básicas de um computador são: processamento de dados, realizado pela CPU; armazenamento de dados, feito pela memória; transferência de dados, realizada pelos dispositivos de entrada e saída; e controle, exercido pela unidade de controle, que coordena todas as operações.**
  
  
## 2. Explique detalhadamente o ciclo de execução de uma instrução em um computador baseado na arquitetura de Von Neumann.

* **O ciclo de execução consiste em três etapas principais: busca, decodificação e execução. Primeiramente, a unidade de controle utiliza o contador de programa (PC) para buscar a instrução na memória. Em seguida, a instrução é decodificada pela UC para determinar a operação a ser realizada. Por fim, a ULA executa a operação e o resultado é armazenado em registradores ou na memória.**
  

## 3. A arquitetura IAS é importante porque ela funciona como um algortmo para o processador do computador, explicando como um sistema deve funcionar. 

* **É uma implementação real do modelo de Von Neumann. A arquitetura IAS foi uma das primeiras implementações práticas do modelo de Von Neumann. Desenvolvida no Instituto de Estudos Avançados de Princeton, ela introduziu o conceito de programa armazenado e serviu de base para os computadores modernos.**
  
  
## 4. Explique o funcionamento dos seguintes registradores da IAS:

* MAR: Guarda o endereço de memória que será acessada. 
* MBR: Guarda temporariamente dados ou instruções. 
* IR: Guarda a instrução atual 
* IBR: Guarda temporariamente a instrução futura. 
* PC: Guarda o endereço de uma próxima instrução 
* AC: Guarda temporariamente dados executados pela ULA 
* MQ: armazena quocientes ou multiplicação


## 5. Descreva o **fluxo de execução de uma instrução na IAS**, citando os registradores envolvidos.

* **O PC guarda o endereço de instrução e passa para o MAR que guarda o endereço de memória para a execução, a instrução vai para MBR, passa pela IR E IBR que guarda a instrução atual e a proxima instrução sequencialmente, agora entra a parte do UC que decodifica a instrução e usa ULA, MQ para fazer contas e voltar para o acumulador.**
  

## 6. O que é ISA?

* **É o conjunto de instruções que o processador consegue entender e executar.**
  
  
## 7. Descreva o formato de uma instrução na arquitetura IAS, explicando o papel do opcode e do operando. 

* **Cada palavra de memória possui 40 bits e pode armazenar duas instruções de 20 bits. Cada instrução é composta por 8 bits de opcode, que indicam a operação, e 12 bits de operando, que indicam o endereço do dado na memória.**
  

## 8. Explique os principais tipos de instruções presentes em um ISA e dê exemplos de cada tipo.

* **Transferência de dados: store (guardar na memória), aritmetricas (soma e subtração), lógicas (and e or), Controle (Jump)**
  
  
## 9. Explique como uma instrução como ADD X é executada pelo processador, desde a busca até o resultado.

* **Busca instrução pelo UC, ele entende e codifica (somar), vai até o endereço (creio que seja através do PC) pega o valor e soma com o que tem no acumulador e volta para o acumulador.**