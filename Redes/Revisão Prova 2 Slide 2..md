
# RESUMO DE ESTUDO SLIDE 2.

| Tópico                                                      | Frequência |     |     |
| ----------------------------------------------------------- | ---------- | --- | --- |
| Aprendizagem de switch (tabela MAC, flooding)               | +++        |     |     |
| CSMA/CD e backoff exponencial                               | +++        |     |     |
| STP (finalidade)                                            | ++         |     |     |
| Diferença hub x switch x bridge                             | ++         |     |     |
| Meios/padrões físicos Ethernet (10BASE-T, 100BASE-TX, etc.) | ++         |     |     |
| Cabeamento estruturado (backbone, horizontal, patch panel)  | ++         |     |     |
| VLANs                                                       | +          |     |     |
| Fibra óptica (núcleo, casca, modos)                         | +          |     |     |

---
# Endereço Unicast e Multicast

Unicast: 0 
Multicast: 1

# Importante:

O bit menos significativo do primeiro byte define o tipo de endereço. Se for 0 é Unicast e se for 1 é Multicast.

Broadcast: é um caso especial de multicast porque todos os bits são iguais a 1.

Verifique o tipo de endereço destino: 4A : 30 : 10 : 21 : 10 : 1A

Solução: para determinar o tipo de endereço, você verifica o segundo dígito hexadecimal, se for par, o endereço é UNICAST, se for ímpar, é MULTICAST. Se todos forem F o endereço é broadcast.

Nesse caso acima o segundo dígito é A, em binário A é 1010, ou seja, par, sendo UNICAST.

# Fast Ethernet:

Os três meios de transmissão que podem ser usadas no Fast Ethernet são:
* Fibra óptica no multimodo.
* Cat 5.
* Cat 3.
  

# Bridge:

É um dispositivo de hardware que tem a possibilidade de se conectar mais de um pc por porta (conjunto de PCs de um mesmo barramento) e o switch conecta 1 PC por porta.
É um dispositivo com poucas portas que conecta segmentos de rede. As diferenças dele para o SWITCH é que ele possui poucas portas e o SWITCH possui muitas portas, o processamento do SWITCH é mais rápido e a latência do BRIDGE é maior.

#### Domínio de colisão: 

- **Sem bridge**: todos os hosts no mesmo domínio de colisão.
    
- **Com bridge**: cada porta da bridge é um domínio de colisão separado.

✅ **Prova pergunta:** “Quantos domínios de colisão tem um switch de 24 portas?”  
Resposta: **24** (cada porta é um domínio).


# Full-duplex Ethernet 

- Usa **dois pares de cabos** (um para enviar, outro para receber).
    
- **Sem colisões**.
    
- Taxa efetiva = dobro (ex: 100 Mbps full-duplex = 200 Mbps total).
  
  
# APRENDIZAGEM DE SWITCH (TABELA MAC, FLOODING, ENCAMINHAMENTO)

### 🔹 Tabela MAC (ou tabela de comutação / tabela de encaminhamento)

- É uma **memória interna do switch**
    
- Armazena: **endereço MAC** ↔ **porta**
    
 

### 🔹 Como o switch aprende? (regra nº 1)

> **Quando um quadro chega em uma porta, o switch aprende o endereço MAC de origem e associa com a porta de chegada.**

Exemplo:  
Chega um quadro na porta 3, endereço de origem = CC:CC:CC:CC:CC:CC  
→ switch insere na tabela: `(3, CC:CC:CC:CC:CC:CC)`

> ⚠️ **Atenção:** o switch **só aprende endereços de origem**. O endereço de destino é usado para **encaminhar**, não para aprender.


### 🔹 Como o switch encaminha? (regras nº 2, 3 e 4)

| Situação                                    | Ação do switch                                         | Nome técnico            |
| ------------------------------------------- | ------------------------------------------------------ | ----------------------- |
| Destino **está na tabela**                  | Encaminha **só para aquela porta**                     | Encaminhamento seletivo |
| Destino **não está na tabela**              | Encaminha para **todas as portas, exceto a de origem** | Flooding (inundação)    |
| Destino = **broadcast** (FF:FF:FF:FF:FF:FF) | Encaminha para **todas as portas, exceto a de origem** | Flooding                |
| Porta de destino = porta de origem          | **Descarta** o quadro (não encaminha)                  | Filtragem               |

## Dicas para nunca errar na prova

1. **Sempre aprenda primeiro o endereço de origem** (antes de encaminhar).
    
2. **Nunca confunda:** origem = aprende, destino = consulta.
    
3. **Se destino não está na tabela** → flooding (todas as portas menos a de origem).
    
4. **Se destino está na tabela** → encaminha só para aquela porta.
    
5. **A tabela só mostra endereços já aprendidos** (nunca coloque destino antes de ele aparecer como origem).
    
6. **O switch não aprende endereço de destino** (só de origem).
   
   
# O que é CSMA/CD?

**Sigla:**

- **CS** = Carrier Sense (detecção de portadora)
    
- **MA** = Multiple Access (acesso múltiplo)
    
- **CD** = Collision Detection (detecção de colisão)
    

### Tradução direta:

> "Escuto antes de falar, e se houver briga, paro de falar e tento de novo depois."


### O problema que o CSMA/CD resolve

Em uma rede Ethernet **compartilhada** (barramento, hub, ou mesmo rádio), **vários nós tentam falar ao mesmo tempo** no mesmo meio físico.

Se dois ou mais transmitem ao mesmo tempo → **colisão** → os dados se corrompem.

O CSMA/CD é o **protocolo de acesso ao meio** que evita ao máximo e trata colisões.


## As 4 perguntas que o CSMA/CD responde (cai direto na prova)

| Pergunta                                             | Resposta do CSMA/CD                                                              |
| ---------------------------------------------------- | -------------------------------------------------------------------------------- |
| **1. Quando a estação pode acessar o meio?**         | Quando o meio está **livre** (detecta portadora)                                 |
| **2. O que fazer se o meio está ocupado?**           | Espera e tenta de novo (persistência 1-persistente)                              |
| **3. Como saber se a transmissão foi bem-sucedida?** | Detecta **colisão** durante a transmissão                                        |
| **4. O que fazer se ocorrer colisão?**               | Para de transmitir, envia um sinal de **jam**, e executa **backoff exponencial** |

## 4. Funcionamento detalhado (passo a passo)

### 🔹 Etapa 1: Carrier Sense (escuta antes de falar)

- A estação **escuta** o meio (cabo) para ver se alguém está transmitindo.
    
- Se o meio está **livre** → começa a transmitir imediatamente.
    
- Se o meio está **ocupado** → espera até ficar livre.
    

> Isso se chama **1-persistente**: a estação "persiste" em tentar assim que o meio fica livre.

---

### 🔹 Etapa 2: Transmissão

- A estação começa a enviar o quadro.
    
- Durante a transmissão, ela **continua escutando** (detecção de colisão).
    

---

### 🔹 Etapa 3: Detecção de colisão

- Colisão ocorre quando **dois ou mais nós transmitem ao mesmo tempo**.
    
- Como detectar?  
    O sinal no cabo fica **acima do normal** (tensão maior que o esperado para um único transmissor).
    

Quando detecta colisão:

1. Para de transmitir **imediatamente** (não termina o quadro).
    
2. Envia um sinal de **jam** (32 bits de 1s) para garantir que todos os nós percebam a colisão.
    
3. Aborta a transmissão.
    

---

### 🔹 Etapa 4: Backoff exponencial (a parte que mais cai em prova)

- Após uma colisão, a estação **espera um tempo aleatório** antes de tentar novamente.
    
- Esse tempo é um **múltiplo inteiro** do **slot time** (tempo de um slot).
    
- O número de slots possíveis **dobra a cada nova colisão** para o mesmo quadro. 
### Padrão 2 (backoff exponencial)

> _Dois nós A e B colidem. Pode haver nova colisão nas retransmissões? Justifique._

**Resposta:**  
Sim, pode. Após a primeira colisão, cada nó escolhe um número aleatório entre 0 e 1 slot. Se ambos escolherem 0, transmitem juntos novamente, gerando nova colisão. A cada nova colisão, o intervalo dobra, reduzindo a probabilidade, mas não eliminando.


## O que é STP?

### Tradução direta:

> "Um protocolo que transforma uma rede com **caminhos redundantes** (que criam loops) em uma **árvore lógica sem loops**."

## O problema que o STP resolve

### 🔹 Redes com redundância (loops)

Em redes grandes, colocamos **caminhos redundantes** (mais de um caminho entre switches) para:

- Aumentar a **disponibilidade** (se um cabo quebrar, outro caminho funciona)
    
- Balancear carga (em alguns casos)
    

### 🔹 O problema do loop

Quando há loops na rede **sem STP**, acontece:

| Problema                        | O que acontece                                                                 |
| ------------------------------- | ------------------------------------------------------------------------------ |
| **Tempestade de broadcast**     | Um quadro de broadcast (ex: ARP) fica circulando para sempre, multiplicando-se |
| **Duplicação de quadros**       | O mesmo quadro chega ao destino por vários caminhos                            |
| **Instabilidade na tabela MAC** | O switch aprende o mesmo endereço em portas diferentes, mudando o tempo todo   |

> ⚠️ **Isso derruba a rede!** O STP foi criado para evitar isso.


## Funcionamento básico do STP (o que você precisa saber para a prova)

### 🔹 Ideia central

O STP **desabilita logicamente** (bloqueia) algumas portas dos switches para que exista **apenas um único caminho ativo** entre qualquer par de switches.

### 🔹 Se um caminho falha

O STP **reabilita** uma porta bloqueada automaticamente, restaurando a conectividade.

> ✅ **Decore:** O STP mantém a redundância física, mas cria uma **topologia lógica sem loops**.


## Como a questão aparece na prova (padrões)

### Qual a finalidade do protocolo Spanning Tree (STP) em bridges e switches?

**Resposta (modelo):**

> O STP evita a formação de loops em redes com caminhos redundantes. Ele desabilita logicamente algumas portas dos switches para que exista apenas um único caminho ativo entre quaisquer dois switches, prevenindo tempestades de broadcast, duplicação de quadros e instabilidade na tabela MAC. Em caso de falha de um caminho ativo, o STP reabilita automaticamente uma porta bloqueada para restaurar a conectividade.


### Em que tipo de situação deve-se adotar switches com suporte a STP e qual o benefício?

**Resposta:**

> Deve-se adotar STP em redes que possuem **caminhos redundantes** entre switches (ex: anéis, malhas). O benefício é **alta disponibilidade**: se um enlace falha, o STP ativa um caminho alternativo automaticamente, sem intervenção manual.


## Dicas para nunca errar na prova

1. **Decore a finalidade principal:** evitar loops em redes redundantes.
    
2. **Lembre sempre:** o STP não remove o cabo físico, só **desabilita logicamente** a porta.
    
3. **Se a pergunta for "quando usar"** → resposta: redes com caminhos redundantes para alta disponibilidade.
   
   
# DIFERENÇA ENTRE HUB, BRIDGE E SWITCH

##  Visão geral (o que cada um faz)

|Dispositivo|Camada OSI|O que faz|Inteligência|
|---|---|---|---|
|**Hub**|Física (camada 1)|Repete o sinal para todas as portas|Nenhuma|
|**Bridge**|Enlace (camada 2)|Filtra quadros por endereço MAC|Pouca (software)|
|**Switch**|Enlace (camada 2)|Encaminha quadros por endereço MAC|Muita (hardware)|

> ⚠️ **Decore:** Hub = burro, Bridge = menos burro, Switch = inteligente.
   

## Hub (repetidor multiporta)

### 🔹O que é?

- Um hub é um **repetidor** com várias portas.
  
### 🔹Como funciona?

- Recebe um sinal elétrico em uma porta.
    
- **Regenera** o sinal (não apenas amplifica – limpa o ruído).
    
- Envia o sinal para **todas as outras portas**, exceto a de origem.
  
### 🔹 Características importantes:

|Característica|O que significa|
|---|---|
|**Compartilhamento de largura de banda**|Se hub tem 10 Mbps e 8 hosts, a largura é dividida entre eles|
|**Um único domínio de colisão**|Se dois hosts transmitirem juntos, colidem|
|**Um único domínio de broadcast**|Um quadro de broadcast chega a todos|
|**Half-duplex apenas**|Não pode enviar e receber ao mesmo tempo|

##  Bridge (ponte)

### 🔹 O que é?

- Uma bridge é um dispositivo de **camada 2** (enlace de dados).
    
- Tem **poucas portas** (geralmente 2 a 4).
    

### 🔹 Como funciona?

- Examina o **endereço MAC de destino** de cada quadro.
    
- Decide se encaminha ou filtra (descarta) o quadro.
    
- Usa uma **tabela MAC** aprendida por software.
    

### 🔹 Características importantes:

|Característica|O que significa|
|---|---|
|**Filtragem de quadros**|Só envia quadros para o segmento correto|
|**Cria domínios de colisão separados**|Uma colisão em um lado não afeta o outro|
|**Compartilhamento de largura de banda**|Ainda compartilha, mas menos que hub|
|**Processamento por software**|Mais lento que switch|

### 🔹 Exemplo:

> Bridge conecta LAN A (porta 1) e LAN B (porta 2).  
> Quadro de A para A (mesma LAN) → bridge **filtra** (não envia para B).  
> Quadro de A para B → bridge **encaminha** para B.
> ✅ **Isso melhora o desempenho** porque tráfego local não atravessa a ponte.


## Switch

### 🔹 O que é?

- Um switch é **essencialmente uma bridge multiporta e de alta velocidade**.
    
- Opera na **camada 2** (enlace de dados).
    

### 🔹 Como funciona?

- Mesmo princípio da bridge: aprende endereços MAC e encaminha seletivamente.
    
- Mas usa **hardware especializado (ASICs)** para ser muito mais rápido.
    

### 🔹 Características importantes:

| Característica                         | O que significa                           |
| -------------------------------------- | ----------------------------------------- |
| **Muitas portas** (8, 16, 24, 48)      | Conecta muitos hosts diretamente          |
| **Cada porta é um domínio de colisão** | Sem colisões entre portas diferentes      |
| **Full-duplex possível**               | Pode enviar e receber ao mesmo tempo      |
| **Comutação em hardware**              | Muito rápido (microssegundos de latência) |
| **Tabela MAC aprendida**               | Grande capacidade de endereços            |

### 🔹 Exemplo:

> Switch 24 portas. Cada computador conectado a uma porta.  
> A porta 1 envia para porta 2. Ao mesmo tempo, porta 3 pode enviar para porta 4.  
> **Não há colisão** porque os caminhos são isolados.


## Tabela comparativa completa (decore para a prova)

| Característica         | Hub               | Bridge             | Switch          |
| ---------------------- | ----------------- | ------------------ | --------------- |
| Camada OSI             | 1 (Física)        | 2 (Enlace)         | 2 (Enlace)      |
| Processamento          | Sinal elétrico    | Software           | Hardware (ASIC) |
| Nº típico de portas    | 4–24              | 2–4                | 8–48            |
| Aprende endereços MAC? | ❌ Não             | ✅ Sim              | ✅ Sim           |
| Filtra quadros?        | ❌ Não             | ✅ Sim              | ✅ Sim           |
| Domínios de colisão    | 1 (todos)         | 1 por porta        | 1 por porta     |
| Full-duplex            | ❌ Não             | ❌ Não (geralmente) | ✅ Sim           |
| Latência               | Baixa (repetição) | Média              | Muito baixa     |
| Custo                  | Baixo             | Médio              | Médio/alto      |

## Como a questão aparece na prova (padrões)

### 🔹 Padrão 1 (diferença direta – mais comum)

> _Por que os switches têm melhor desempenho que os hubs?_

**Resposta (modelo):**

> Os switches têm melhor desempenho porque cada porta é um domínio de colisão independente, permitindo transmissões simultâneas sem colisões. Além disso, switches operam em full-duplex, dobrando a capacidade efetiva, enquanto hubs operam em half-duplex e compartilham a largura de banda entre todas as portas.


### 🔹 Padrão 2 (bridge vs switch)

> _Qual a diferença entre bridges e switches?_

**Resposta (modelo):**

> Tanto bridges quanto switches operam na camada 2 e usam endereços MAC para encaminhamento. A diferença principal é que switches têm muito mais portas (8 a 48) e usam comutação em hardware (ASICs), tornando-os muito mais rápidos. Bridges geralmente têm poucas portas (2 a 4) e usam processamento por software, sendo mais lentos.


### 🔹Padrão 3 (domínio de colisão)

> _Uma LAN Ethernet com 24 computadores conectados por um hub de 10 Mbps. Isso significa que cada computador pode transmitir a 10 Mbps simultaneamente?_

**Resposta (modelo):**

> Não. Em um hub, a largura de banda de 10 Mbps é compartilhada entre todos os 24 computadores. Além disso, todos estão no mesmo domínio de colisão, então apenas um computador pode transmitir por vez. O desempenho efetivo por computador é muito menor que 10 Mbps.


# MEIOS FÍSICOS ETHERNET

## O que significa a nomenclatura?

A nomenclatura Ethernet segue um padrão:

**Exemplo: 10BASE-T**

| Parte    | Significado                                                                                                                         |
| -------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| **10**   | Taxa em Mbps (10 = 10 Mbps, 100 = 100 Mbps, 1000 = 1 Gbps)                                                                          |
| **BASE** | Banda base (transmissão digital direta, sem modulação em portadora)                                                                 |
| **T**    | Meio físico (T = par trançado por UTP, F = fibra, SX = fibra multimodo curta, LX = fibra longa, TX = cabo par trançado por UTP/STP) |


> ⚠️ **Decore:** A letra após o hífen indica o **meio de transmissão**.


## Tabela completa dos padrões que caem na prova

### 🔹 Ethernet (10 Mbps)

|Padrão|Taxa|Meio físico|Distância máx|Codificação|Obs.|
|---|---|---|---|---|---|
|**10BASE5**|10 Mbps|Coaxial grosso (amarelo)|500 m|Manchester|Obsoleto|
|**10BASE2**|10 Mbps|Coaxial fino (RG-58)|185 m|Manchester|Obsoleto|
|**10BASE-T**|10 Mbps|Par trançado Cat3 ou superior|100 m|Manchester|Ainda usado|
|**10BASE-F**|10 Mbps|Fibra óptica multimodo|2 km|Manchester|Raro|

### 🔹Fast Ethernet (100 Mbps)

|Padrão|Taxa|Meio físico|Distância máx|Codificação|Pares/fibras|
|---|---|---|---|---|---|
|**100BASE-TX**|100 Mbps|UTP Cat5 ou superior|100 m|MLT-3 + 4B/5B|2 pares|
|**100BASE-T4**|100 Mbps|UTP Cat3 ou superior|100 m|8B/6T|4 pares|
|**100BASE-FX**|100 Mbps|Fibra multimodo|2 km|NRZ + 4B/5B|2 fibras|

> ✅ **Decore:** O mais comum é **100BASE-TX** (Cat5, MLT-3, 2 pares).
>

## Tabela de decoreba rápida para a prova

| Padrão      | Taxa     | Meio               | Distância | Codificação principal |
| ----------- | -------- | ------------------ | --------- | --------------------- |
| 10BASE-T    | 10 Mbps  | Par trançado Cat3  | 100 m     | Manchester            |
| 100BASE-TX  | 100 Mbps | Par trançado Cat5  | 100 m     | MLT-3 + 4B/5B         |
| 100BASE-FX  | 100 Mbps | Fibra multimodo    | 2 km      | NRZ + 4B/5B           |
| 1000BASE-T  | 1 Gbps   | Par trançado Cat5e | 100 m     | PAM5                  |
| 1000BASE-SX | 1 Gbps   | Fibra multimodo    | 550 m     | 8B/10B                |
| 1000BASE-LX | 1 Gbps   | Fibra monomodo     | 5 km      | 8B/10B                |
## Dicas para nunca errar na prova

1. **BASE** significa banda base (sinal digital direto, sem modulação).
    
2. **T** = par trançado (Twisted pair), **F** = fibra (Fiber).
    
3. **SX** = multimodo curto (850 nm), **LX** = monomodo longo (1310 nm).
    
4. **Distâncias:** par trançado = 100 m, fibra multimodo = 550 m a 2 km, fibra monomodo = 5 a 10 km.
    
5. **100BASE-TX** usa **2 pares** (um para enviar, um para receber).
    
6. **1000BASE-T** usa **4 pares** (todos transmitem e recebem).
   


# CABEAMENTO ESTRUTURADO

### 🔹 Parte 1 – Área de trabalho (Work Area)

| Característica   | Descrição                                                                                   |
| ---------------- | ------------------------------------------------------------------------------------------- |
| **Onde fica**    | No ambiente do usuário (escritório, sala, laboratório)                                      |
| **O que contém** | Tomada de parede (jack), cabo patch cord, equipamento do usuário (PC, telefone, impressora) |
✅ **Decore:** Área de trabalho = onde o usuário conecta seu equipamento.

### 🔹Parte 2 – Cabeamento horizontal (Horizontal Cabling)

| Característica   | Descrição                                                                 |
| ---------------- | ------------------------------------------------------------------------- |
| **Onde fica**    | Entre a área de trabalho e o armário de telecomunicações (no mesmo andar) |
| **O que contém** | Cabos que vão da tomada da parede até o patch panel do andar              |
✅ **Decore:** Cabeamento horizontal = **o cabo que vai da tomada do usuário até o armário do andar.**

### 🔹 Parte 3 – Armário de telecomunicações (Telecommunications Room / Closet)

| Característica   | Descrição                                                      |     |
| ---------------- | -------------------------------------------------------------- | --- |
| **Onde fica**    | Em cada andar do prédio                                        |     |
| **O que contém** | Patch panel, switches, hubs, roteadores, servidores (às vezes) |     |
| **Função**       | Concentra os cabos horizontais do andar e conecta ao backbone  |     |
✅ **Decore:** Armário de telecomunicações = **a salinha em cada andar onde ficam os equipamentos de rede.**

### 🔹 Parte 4 – Patch Panel (painel de conexão)

| Característica | Descrição                                                                         |
| -------------- | --------------------------------------------------------------------------------- |
| **O que é**    | Um painel com conectores RJ-45 (ou outros) na frente e terminações de cabos atrás |
| **Onde fica**  | Dentro do armário de telecomunicações                                             |
| **Função**     | Organiza e permite mudanças rápidas (usando patch cords) sem religar cabos        |
| **Vantagem**   | Flexibilidade e facilidade de manutenção                                          |
✅ **Decore:** Patch Panel = **O painel que organiza os cabos para facilitar mudanças.**

### 🔹 Parte 5 – Cabeamento vertical ou backbone (Backbone Cabling)

| Característica    | Descrição                                                                             |
| ----------------- | ------------------------------------------------------------------------------------- |
| **Onde fica**     | Entre andares (vertical) ou entre prédios (campus)                                    |
| **O que conecta** | Armários de telecomunicações de andares diferentes, ou sala de equipamentos principal |
| **Função**        | Transporta tráfego agregado de vários andares                                         |
✅ **Decore:** Cabeamento vertical ou backbone = **o cabo que liga os armários dos andares entre si.**

### 🔹 Parte 6 – Sala de equipamentos (Equipment Room)

|Característica|Descrição|
|---|---|
|**Onde fica**|Geralmente no térreo ou em um andar central|
|**O que contém**|Switches centrais, roteadores, servidores principais, PABX, provedor de Internet|
|**Função**|Ponto central de distribuição do backbone|
✅ **Decore:** Sala de equipamentos = **a sala principal onde fica o centro da rede.**


## 📌 4. Distâncias máximas (decore!)

| Tipo de cabeamento               | Distância máxima |
| -------------------------------- | ---------------- |
| Patch cord (área de trabalho)    | 5 m              |
| Cabeamento horizontal            | 90 m             |
| Total (horizontal + patch cords) | 100 m            |
| Backbone (par trançado)          | 90 m             |
| Backbone (fibra multimodo)       | 550 m a 2 km     |
| Backbone (fibra monomodo)        | 5 km a 10 km     |

## Como a questão aparece na prova (padrões)

### 🔹 Padrão 1 (definição de termos – bônus)

> _Em sistema de cabeamento estruturado, definir: a) cabeamento vertical ou backbone b) áreas de trabalho_

**Resposta (modelo):**

> **a) Cabeamento vertical ou backbone:** é o cabeamento que conecta os armários de telecomunicações de diferentes andares (dentro de um prédio) ou diferentes prédios (em um campus). Ele forma a espinha dorsal da rede e geralmente utiliza fibra óptica devido às maiores distâncias e maior largura de banda necessária.
> 
> **b) Áreas de trabalho:** é o local onde os equipamentos dos usuários (computadores, telefones, impressoras) se conectam à rede. Inclui a tomada de parede, o patch cord e o próprio equipamento. É o ponto final do cabeamento estruturado.

---

### 🔹 Padrão 2 (projeto – recomendar meios)

> _Você foi contratado para projetar o cabeamento de uma universidade com 2 prédios, 6 andares cada (18 m de altura), distância entre prédios 150 m. Recomendar meios para: a) backbone vertical b) horizontal c) entre prédios._

**Resposta (modelo):**

> **a) Backbone vertical (dentro de cada prédio):** como a altura é de apenas 18 m, poderia usar par trançado Cat6 (90 m máximo), mas considerando agregação de tráfego e futura expansão, recomendo **fibra óptica multimodo (1000BASE-SX)** para maior largura de banda e imunidade a interferências.
> 
> **b) Cabeamento horizontal (dentro do andar):** para Fast Ethernet (100 Mbps), recomendo **UTP Cat5e** (até 100 m). Se houver orçamento, **Cat6** para futura expansão a 1 Gbps.
> 
> **c) Entre prédios (150 m):** par trançado não atende (limite 100 m). Recomendo **fibra óptica multimodo (1000BASE-SX)** ou **monomodo (1000BASE-LX)** para maior distância e imunidade a descargas atmosféricas.

---

### 🔹 Padrão 3 (finalidade do patch panel)

> _Qual a finalidade do Patch Panel nos racks de redes?_

**Resposta (modelo):**

> O Patch Panel serve para organizar e facilitar as conexões entre os cabos do cabeamento horizontal (que vêm das tomadas) e os equipamentos ativos (switches). Ele permite que mudanças de conexão sejam feitas rapidamente, trocando apenas os patch cords frontais, sem necessidade de religar os cabos no conector traseiro. Isso aumenta a flexibilidade, facilita a manutenção e melhora a organização do rack.


## Tabela de decoreba rápida para a prova

|Parte|Onde fica|Meio típico|Distância|
|---|---|---|---|
|Área de trabalho|Mesa do usuário|Patch cord (Cat5e/Cat6)|3–5 m|
|Horizontal|Dentro do andar|UTP Cat5e/Cat6|90 m|
|Armário|Em cada andar|-|-|
|Patch Panel|Dentro do armário|-|-|
|Backbone (vertical)|Entre andares|Fibra ou Cat6|Até 90 m|
|Sala de equipamentos|Térreo/central|-|-|
|Backbone (campus)|Entre prédios|Fibra (multimodo/monomodo)|Até 5 km+|


# VLANs (VIRTUAL LANS)

## O que é VLAN? (explicação simples)

### 🔹 Sem termos técnicos:

> **VLAN é como se você pegasse um switch grande e dividisse em vários switches menores, só que por software.**

### 🔹 Exemplo prático:

Imagine um switch de 24 portas no seu escritório.

- **Sem VLAN:** todos os 24 computadores se enxergam como se estivessem na mesma sala. Se um mandar mensagem para todos (broadcast), todo mundo recebe.
    
- **Com VLAN:** você pode separar, por exemplo:
    
    - VLAN 10 → portas 1 a 8 (RH)
        
    - VLAN 20 → portas 9 a 16 (Vendas)
        
    - VLAN 30 → portas 17 a 24 (TI)
        

Agora, um computador do RH **não enxerga** os computadores de Vendas, a menos que um roteador conecte as VLANs.

## Para que serve a VLAN? (vantagens principais)

| Vantagem                 | Explicação simples                                                                          |
| ------------------------ | ------------------------------------------------------------------------------------------- |
| **Segurança**            | Computadores de setores diferentes não se enxergam                                          |
| **Menos tráfego inútil** | Mensagens de "alô, alguém aí?" (broadcast) ficam só dentro da VLAN, não vão para todo mundo |
| **Flexibilidade**        | Mudar um computador de setor é só trocar a configuração da porta, não precisa religar cabos |
| **Economia**             | Não precisa comprar vários switches pequenos; um switch grande resolve                      |

##  Frases prontas para decorar (versão super simplificada)

### 🔹 O que é VLAN?

> **É uma tecnologia que permite segmentar uma única rede física em múltiplas redes lógicas independentes

### 🔹 Para que serve?

> **Para isolar o tráfego, aumentar a segurança e reduzir mensagens inúteis na rede.**

### 🔹 Como melhora o desempenho?

> **Diminui o número de computadores que recebem mensagens de "alô, alguém aí?" (broadcast), deixando a rede mais rápida.**

### 🔹 O que precisa para duas VLANs se falarem?

> **Precisa de um roteador.**


## Como a questão aparece na prova

### 🔹 Padrão 1 (o que são VLANs)

> _O que são VLANs?_

**Resposta (use a frase decorada):**

> VLAN é uma forma de dividir um switch em redes menores, só por software, sem precisar de vários switches físicos.

---

### 🔹 Padrão 2 (vantagens)

> _Como as VLANs podem melhorar o desempenho de uma LAN Ethernet?_

**Resposta (use a frase decorada):**

> As VLANs melhoram o desempenho porque diminuem o número de computadores que recebem mensagens de broadcast (como "alô, alguém aí?"). Isso reduz tráfego desnecessário e deixa a rede mais rápida. Além disso, aumentam a segurança isolando setores diferentes.

---

### 🔹 Padrão 3 (broadcast domain)

> _O que é domínio de broadcast em VLANs?_

**Resposta (simplificada):**

> Dentro de uma VLAN, todos os computadores recebem as mensagens de broadcast. VLANs diferentes não recebem broadcast umas das outras. Ou seja, **cada VLAN é um domínio de broadcast separado**.


# FIBRA ÓPTICA


É um fio que transmite dados.

### 🔹 Núcleo

> **É o miolo da fibra, por onde a luz viaja.**

### 🔹 Casca

> **É a capa que envolve o núcleo e segura a luz dentro dele.**

## Tipos de fibra óptica (o que mais cai)

### 🔹 Fibra multimodo x monomodo

| Tipo          | Explicação simples                    | Distância                | Cor do conector (às vezes) |
| ------------- | ------------------------------------- | ------------------------ | -------------------------- |
| **Multimodo** | Vários caminhos de luz (vários modos) | Curta (até 550 m)        | Bege ou preto              |
| **Monomodo**  | Um único caminho de luz (um modo)     | Longa (até 5 km ou mais) | Azul                       |

### 🔹 Frases prontas para decorar:

**Multimodo:**

> A luz vai por vários caminhos dentro do núcleo. Serve para distâncias curtas.

**Monomodo:**

> A luz vai por um único caminho. Serve para distâncias longas.

### 🔹 Fibra multimodo de índice degrau (step-index)

| Característica     | Explicação simples                                                         |
| ------------------ | -------------------------------------------------------------------------- |
| **O que é**        | O índice de refração muda de repente (degrau) do núcleo para a casca       |
| **Caminho da luz** | A luz vai **zigue-zague**, batendo nas bordas                              |
| **Problema**       | Os raios de luz chegam em tempos diferentes → sinal se espalha (dispersão) |
**Frase pronta:**

> A luz vai zigue-zague, batendo nas bordas. Isso espalha o sinal.

### 🔹 Fibra multimodo de índice gradual (graded-index)

|Característica|Explicação simples|
|---|---|
|**O que é**|O índice de refração diminui **aos poucos** do centro para a borda|
|**Caminho da luz**|A luz vai **curvando** suavemente, não bate nas bordas|
|**Vantagem**|Os raios de luz chegam em tempos **mais parecidos** → menos espalhamento|

**Frase pronta:**

> A luz vai curvando suavemente. O sinal chega mais junto e mais rápido.


### Tabela comparativa (decore assim)

| Tipo           | Caminho da luz        | Problema / Vantagem                      |
| -------------- | --------------------- | ---------------------------------------- |
| Índice degrau  | Zigue-zague (batendo) | Luz chega em tempos diferentes (ruim)    |
| Índice gradual | Curvado (suave)       | Luz chega em tempos mais parecidos (bom) |

### 🔹 Núcleo

> É o miolo da fibra. A luz viaja dentro dele.

### 🔹 Casca

> É a capa que segura a luz dentro do núcleo.

### 🔹 Fibra multimodo

> Vários caminhos de luz. Serve para distâncias curtas.

### 🔹 Fibra monomodo

> Um caminho de luz. Serve para distâncias longas.

### 🔹 Índice degrau

> A luz vai zigue-zague. O sinal se espalha.

### 🔹 Índice gradual

> A luz vai curvando. O sinal chega mais junto.


## Como a questão aparece na prova

### 🔹 Padrão 1 (núcleo e casca)

> _A estrutura de um cabo de fibra óptica é composta por núcleo e casca. Qual o propósito da casca? E do núcleo?_

**Resposta (use as frases decoradas):**

> O núcleo é o miolo da fibra por onde a luz viaja. A casca é a capa que envolve o núcleo e tem a função de segurar a luz dentro dele, impedindo que ela escape.
---

### 🔹 Padrão 2 (índice degrau x gradual)

> _Qual a diferença entre as fibras ópticas multimodo de índice degrau e de índice gradual?_

**Resposta (use as frases decoradas):**

> Na fibra de índice degrau, a luz vai em zigue-zague, batendo nas bordas do núcleo, o que faz os raios de luz chegarem em tempos diferentes, espalhando o sinal. Na fibra de índice gradual, o índice de refração diminui suavemente do centro para a borda, fazendo a luz curvar suavemente, o que reduz o espalhamento e faz o sinal chegar em tempos mais parecidos.


