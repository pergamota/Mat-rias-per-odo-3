
# 🧠 1. Camada Física (Fundamentos)

## 📌 O que é a camada física?

- É a **camada 1 do modelo OSI**
- Responsável por:
    - Transmissão de bits (0 e 1)
    - Definição do meio físico
    - Sinal elétrico, óptico ou eletromagnético

## ⚠️ Cai MUITO em prova:

- Ela **não interpreta dados**, só transmite
- Trabalha com:
    - tensão
    - frequência
    - sincronização

---

# 🌐 2. Topologias de Rede

## 📌 Tipos principais

### 🔹 Ponto-a-ponto

- Ligação direta entre 2 dispositivos

### 🔹 Multiponto

- Vários dispositivos compartilham o meio

---

## 📌 Topologias físicas

### ⭐ 1. Estrela

- Todos ligados a um dispositivo central (switch/hub)
- 🔥 MAIS COBRADA

📌 Fórmula:

- Número de links = **n**

📌 Vantagens:

- Fácil manutenção
- Isolamento de falhas

📌 Desvantagens:

- Dependência do dispositivo central

---

### 🕸️ 2. Malha (Mesh)

- Todos conectados com todos

📌 Fórmula:

- Links = **n(n-1)/2**

📌 Vantagens:

- Alta confiabilidade

📌 Desvantagem:

- Custo altíssimo

---

### 🧵 3. Barramento

- Um único cabo compartilhado

📌 Fórmula:

- 1 cabo

📌 Problemas:

- Colisões
- Difícil diagnóstico

---

### 🔄 4. Anel

- Cada nó conectado ao próximo

📌 Fórmula:

- Links = n

📌 Problema:

- Se um falhar → rede pode cair

---

### 🔀 5. Híbrida

- Combinação (ex: estrela + barramento)

---

## 🎯 Dica de prova:

👉 Professora pode pedir:

- "qual topologia usa menos cabos?"  
    → Barramento
- "qual é mais confiável?"  
    → Malha

---

# Meio Guiado: 

 * São aqueles que possuem meio físico como cabo de par trançado, cabo de fibra óptica.

---


# 🔌 3. Meios de Transmissão (GUIADOS)

## 📌 Definição:

- Meio físico sólido por onde o sinal passa

---

## 🔹 1. Par trançado (UTP / STP)

### 📌 Funcionamento:

- Dois fios trançados → reduz interferência
  
# Blindagem: 

* Transmissão repetida das mesmas informações nos dois fios 
  mas com polaridades invertidas.

### 📌 Tipos:

- UTP → sem blindagem
- STP → com blindagem

### 📌 Categorias:

- Cat5, Cat6, Cat6A...

### 📌 Conceitos IMPORTANTES:

#### 🔸 Atenuação

- Perda de sinal ao longo da distância

#### 🔸 NEXT (Near-End Crosstalk)

- Interferência entre pares

---

## ⚠️ Pegadinha de prova:

👉 UTP usa:

- **conector RJ-45**

---

## 🔹 2. Cabo coaxial

- Mais protegido contra interferência
- Usado em:
    - TV
    - redes antigas

### 📌 Conector:

- BNC

---

## 🔹 3. Fibra óptica

### 📌 Como funciona:

- Transmite luz

### 📌 Tipos:

- Multimodo → curta distância
- Monomodo → longa distância

### 📌 Vantagens:

- Alta velocidade
- Imune a interferência

### 📌 Desvantagens:

- Custo alto

---

## 🎯 Dica da sua prova:

Você acertou isso aqui 👇

> fibra para longas distâncias (entre prédios)

✔️ EXATAMENTE o que cai

---

# Cabeamento Estruturado

## 📌 Vantagens da centralização

- Melhor segurança
- Controle de acesso
- Facilidade de manutenção
- Uso de no-break centralizado

---

## 📌 Desvantagem
 
- Ponto único de falha

---

## 📌 Elementos (CAI MUITO)

### 🔹 1. Sala de equipamentos

- Onde ficam servidores, switches

### 🔹 2. Backbone (vertical)

- Liga andares/prédios

### 🔹 3. Cabeamento horizontal

- Vai até o usuário

📌 Limite:

- **90 metros + 10 metros patch = 100m**

---

### 🔹 4. Armário de telecomunicações

- Interligação

### 🔹 5. Área de trabalho

- Onde o usuário conecta

---

## ⚠️ Pegadinha clássica:

👉 Diferença:

|Tipo|Função|
|---|---|
|Backbone|longa distância|
|Horizontal|até o usuário|

---

## 📌 Normas importantes:

- EIA/TIA-568
- EIA/TIA-569

---

## 📌 Distâncias mínimas (INTERFERÊNCIA)

- 1,20m → motores
- 0,30m → cabos elétricos
- cruzamento → perpendicular

👉 Cai como questão teórica!

---

# 🧩 5. Patch Panel (CAIU NA SUA PROVA)

## 📌 Função REAL:

- Organizar e distribuir cabos
- Facilitar manutenção

## ⚠️ O que a professora espera:

👉 Não é só “organizar cabos”

✔️ Resposta ideal:

- centralizar conexões
- facilitar gerenciamento
- permitir reconfiguração rápida

---

# 🔢 6. Codificação de Linha (MUITO IMPORTANTE)

## 📌 O que é?

- Representar bits como sinais elétricos

---

## 📌 Conceitos-chave:

### 🔹 Taxa de dados (N)

- bits por segundo

### 🔹 Largura de banda (B)

---

## 📌 Fórmula importante:

👉 Relação:

- N = taxa de dados
- B = banda
  
---
## 🔹 2. Manchester (🔥 CAI MUITO)

- Transição no meio do bit

📌 Usado em:

- Ethernet 10 Mbps

📌 Vantagem:

- sincronização

📌 Desvantagem:

- usa mais banda

---

## 🔹 3. MLT-3

- usado em Fast Ethernet

---

## 🔹 4. 4D-PAM5

- usado em Gigabit Ethernet
  
  ---
# 1. O que são LINKS na rede

## 📌 Definição

Um **link** é o **meio físico ou lógico que conecta dois dispositivos** em uma rede.

👉 Exemplos:

- Cabo UTP entre PC e switch → 1 link
- Fibra entre dois prédios → 1 link
- Conexão Wi-Fi → também é um link (sem fio)

---

## 📌 Em topologias (IMPORTANTE)

- Estrela → cada dispositivo tem 1 link com o switch
- Malha → vários links entre todos os dispositivos
- Barramento → 1 único link compartilhado

---

## 🎯 Dica de prova

👉 Se a questão falar:

> "quantidade de links"

Você precisa lembrar das fórmulas:

- Malha: `n(n-1)/2`
- Estrela: `n`
- Barramento: `1`

---

# 🧠 2. HUB vs SWITCH (ESSENCIAL PRA PROVA)

---

## 🔴 HUB

### 📌 O que é:

- Dispositivo de camada **física (camada 1)**
- Funciona como um **repetidor**

### 📌 Como funciona:

- Recebe sinal → replica para TODAS as portas

---

### 📌 Características:

- Não entende endereço MAC
- Não filtra tráfego
- Meio compartilhado

---

### 📌 Problemas:

- Colisões
- Baixo desempenho
- Half-duplex

---

### 📌 Resumo:

👉 HUB = "grita pra todo mundo"

---

## 🟢 SWITCH

### 📌 O que é:

- Dispositivo de camada **2 (enlace)**
- Inteligente

---

### 📌 Como funciona:

- Aprende os endereços MAC
- Cria uma **tabela MAC**

### 🔹 Tabela MAC (ou tabela de comutação / tabela de encaminhamento)

- É uma **memória interna do switch**
    
- Armazena: **endereço MAC** ↔ **porta**
    
- Exemplo:
    

|Porta|Endereço MAC|
|---|---|
|1|AA:AA:AA:AA:AA:AA|
|2|BB:BB:BB:BB:BB:BB|
|5|EE:EE:EE:EE:EE:EE|

- Inicialmente: **vazia** (o switch não sabe quem está onde)

### 🔹 Como o switch aprende? (regra nº 1)

> **Quando um quadro chega em uma porta, o switch aprende o endereço MAC de origem e associa com a porta de chegada.**

Exemplo:  
Chega um quadro na porta 3, endereço de origem = CC:CC:CC:CC:CC:CC  
→ switch insere na tabela: `(3, CC:CC:CC:CC:CC:CC)`

> ⚠️ **Atenção:** o switch **só aprende endereços de origem**. O endereço de destino é usado para **encaminhar**, não para aprender.

---

### 🔹 Como o switch encaminha? (regras nº 2, 3 e 4)

| Situação                                    | Ação do switch                                         | Nome técnico            |
| ------------------------------------------- | ------------------------------------------------------ | ----------------------- |
| Destino **está na tabela**                  | Encaminha **só para aquela porta**                     | Encaminhamento seletivo |
| Destino **não está na tabela**              | Encaminha para **todas as portas, exceto a de origem** | Flooding (inundação)    |
| Destino = **broadcast** (FF:FF:FF:FF:FF:FF) | Encaminha para **todas as portas, exceto a de origem** | Flooding                |
| Porta de destino = porta de origem          | **Descarta** o quadro (não encaminha)                  | Filtragem               |

---

### 📌 Funcionamento detalhado (CAI NA PROVA):

#### 1. Aprendizado

- Quando um quadro chega:
    - Switch aprende:
        - MAC origem
        - porta

#### 2. Encaminhamento

- Se conhece o destino:  
    → envia só para a porta correta

#### 3. Flooding (IMPORTANTE)

- Se NÃO conhece:  
    → envia para TODAS as portas (exceto a de origem)

---

### 📌 Vantagens:

- Sem colisão
- Full duplex
- Melhor desempenho

---

## ⚔️ Comparação direta:

|Característica|HUB|SWITCH|
|---|---|---|
|Camada|1|2|
|Inteligência|Não|Sim|
|MAC|Não usa|Usa|
|Colisão|Sim|Não|
|Desempenho|Baixo|Alto|

---

## 🎯 Dica da sua prova:

👉 Cai exatamente isso:

> "Por que switch é melhor que hub?"

✔️ Resposta ideal:

- evita colisões
- envia apenas para o destino
- melhora desempenho

---

# ⚡ 3. Interferência (RUÍDO)

## 📌 O que é:

Qualquer **distúrbio que afeta o sinal transmitido**

---

## 📌 Tipos:

- Eletromagnética (mais comum)
- Crosstalk (entre cabos)
- Equipamentos elétricos

---

## 📌 Exemplos:

- Motor
- Transformador
- Cabos de energia

---

## 🎯 Consequência:

- Perda de dados
- Erros de transmissão

---

# 🛡️ 4. Blindagem (Shielding)

## 📌 O que é:

Proteção do cabo contra interferência

---

## 📌 Tipos:

### 🔹 UTP (Unshielded)

- Sem blindagem
- Mais barato

### 🔹 STP (Shielded)

- Com blindagem metálica
- Mais protegido

---

## 📌 Como funciona:

- A blindagem impede que ondas externas afetem o sinal
 
---

## 🎯 Dica:

👉 Prova adora perguntar:

- "qual cabo usar em ambiente com interferência?"  
    ✔️ STP ou fibra

---

# 🌐 5. Backbone (BLACKBONE na sua fala)

## 📌 Nome correto:

👉 **Backbone**

---

## 📌 O que é:

- Parte **principal da rede**
- Responsável por conectar grandes segmentos

---

## 📌 Onde aparece:

- Entre prédios
- Entre andares
- Data centers

---

## 📌 Características:

- Alta velocidade
- Alta capacidade
- Geralmente fibra óptica

---

## 📌 No cabeamento estruturado:

👉 Backbone = **cabeamento vertical**

---

## 🎯 Dica de prova:

👉 Se for:

- longa distância → backbone
- curta distância → horizontal

---

# 🏢 6. Cabeamento Estruturado (AGORA COMPLETO MESMO)

---

## 📌 Definição (nível prova)

Sistema padronizado de cabeamento que organiza e integra todos os serviços de rede de forma eficiente, escalável e segura.

---

## 📌 Objetivos:

- Organização
- Padronização
- Facilidade de manutenção
- Escalabilidade

---

## 📌 PRINCIPAIS COMPONENTES (CAI MUITO)

---

## 🔹 1. Entrance Facilities (Entrada)

### 📌 Função:

**Conexão com a rede externa

- Ponto de entrada da rede externa (internet)

---

## 🔹 2. Equipment Room (Sala de Equipamentos)

### 📌 Função: 

**Concentra os equipamentos da rede.

- Onde ficam:
    - servidores
    - switches principais
    - roteadores

---

## 🔹 3. Backbone Cabling (Vertical)

### 📌 Função:

**Liga a sala de equipamentos aos armários de telecomunicações nos andares.

- Liga:
    - sala de equipamentos
    - armários de telecomunicação

### 📌 Características:

- Longas distâncias
- Alta capacidade
- Geralmente fibra

---

## 🔹 4. Telecommunications Closet (Armário)

### 📌 Função:

**Conecta o cabeamento vertical com o cabeamento horizontal.

- Ponto intermediário
- Distribui rede para o andar

---

## 🔹 5. Horizontal Cabling

### 📌 Função:

- Vai do armário até o usuário

### 📌 Limite:

- 90m + 10m patch cord

---

## 🔹 6. Work Area (Área de trabalho)

### 📌 Função:

Espaço onde será conectado o equipamento ao cabeamento.

- Onde o usuário conecta:
    - PC
    - impressora

---

## 🔹 7. Administração

- Documentação e organização

---

## 📊 Estrutura completa:

Internet  
   ↓  
Entrada  
   ↓  
Sala de Equipamentos  
   ↓  
Backbone (vertical)  
   ↓  
Armário de telecom  
   ↓  
Cabeamento horizontal  
   ↓  
Usuário

---

## ⚠️ Regras IMPORTANTES

### 📌 Distâncias:

- Horizontal: 100m máximo

---

### 📌 Interferência:

- 1,20m → motores
- 0,30m → energia
- cruzamento → perpendicular

---

## 🎯 Dica de prova:

👉 Professora pode perguntar:

- "diferença entre backbone e horizontal"
- "função do armário"
- "limite de distância"

---

# 🔲 7. PATCH PANEL (AGORA COMPLETO)

## 📌 O que é?

👉 **NÃO é um dispositivo ativo**

✔️ É um **dispositivo passivo**

---

## 📌 Função:

- Organizar conexões de rede
- Centralizar cabos
- Facilitar manutenção

---

## 📌 Como funciona:

1. Cabos da rede chegam atrás
2. Na frente → portas RJ-45
3. Você usa patch cords para conectar ao switch

---

## 📌 Analogia:

👉 É tipo um "quadro de distribuição"

---

## 📌 Por que usar?

- Evita bagunça
- Facilita troca de conexões
- Evita desgaste nos switches

---

## 📌 Onde fica:

- Rack
- Armário de telecom

---

## ⚠️ Pegadinha:

👉 NÃO faz:

- roteamento
- comutação

---

## 🎯 Resposta ideal de prova:

> Patch panel é um componente passivo que organiza e distribui conexões de rede, facilitando manutenção e gerenciamento.

---
# 🔄 Sincronização (CAI MUITO)

## 📌 Problema:

Transmissor e receptor precisam estar sincronizados.

## 📌 Se não estiver:

- Bits interpretados errado
- Erro de transmissão

Para que os dados sejam interpretadas no receptor, o intervalo de sinalização no receptor tem que bater com o intervalo gerado no transmissor.

 ---
 
# 1. Taxa de Dados (N) vs Largura de Banda (B)

## 📌 Definições fundamentais

- **Taxa de dados (N)** → quantidade de bits por segundo (bps)
- **Largura de banda (B)** → capacidade do canal (Hz)

---

## 📌 Relação entre eles

A transmissão digital depende da relação:

### N= r ⋅ B ⋅ c 

Onde:

- **N** = taxa de dados
- **B** = largura de banda
- **r** = relação entre bits e sinais
- **c** = fator (geralmente 0,5)

---

## 📌 Forma mais usada (Nyquist)

### N = 2B log⁡2 L 

Onde:

- **L** = número de níveis de sinal

---

## 🎯 Interpretação (ESSENCIAL)

- Quanto maior **B**, maior a taxa possível
- Quanto mais níveis (**L**), mais bits por sinal

---

# 📉 2. Largura de Banda Mínima

## 📌 Ideia

Qual o mínimo de banda necessário para transmitir uma taxa N?

---

## 📌 Exemplo clássico (NRZ)

Sabemos que:

### N = 2B 

Então:

### B = N/2 

---

## 🎯 Exemplo (igual prova):

Se:

- N = 10 Mbps

Então:

- B = 5 MHz

---

## ⚠️ Pegadinha:

👉 Manchester NÃO segue isso (usa mais banda)


# 4. Codificação de Linha (ESSENCIAL)

---

# 🔹 NRZ (Non Return to Zero)

## 📌 NRZ-L

- Nível define o bit

## 📌 NRZ-I

- Mudança define o bit

---

## 📌 Relação:

##### N = 2B 

---

## ⚠️ Problema:

- Não garante sincronização

---

# 🔴 5. Manchester (CAI MUITO)

## 📌 Característica PRINCIPAL:

👉 Sempre há uma transição no meio do bit

---

## 📌 Regras:

|Bit|Transição|
|---|---|
|0|alta → baixa|
|1|baixa → alta|

---

## 📌 Vantagem:

- Sincronização perfeita

## 📌 Desvantagem:

- Usa mais banda

---

## 📌 Relação:

#### N = B

---

## ⚠️ IMPORTANTE:

👉 Manchester usa **o dobro da banda do NRZ**

---

# ✍️ 6. COMO DESENHAR MANCHESTER (CAI NA PROVA)

---

## 📌 Passo a passo:

1. Pegue o bit
2. Divida o tempo em 2 partes
3. Faça transição no meio

---

## 📌 Exemplo: letra "R"

ASCII de R:

R = 01010010

---

## 📌 Construção:

|Bit|Manchester|
|---|---|
|0|↓|
|1|↑|

---

## 🎯 Dica:

👉 Sempre tem mudança no meio do bit

---

# 📊 7. OUTRAS CODIFICAÇÕES IMPORTANTES

---

## 🔹 RZ (Return to Zero)

- Volta ao zero no meio
- Mais seguro que NRZ
- Mais banda

---

## 🔹 MLT-3

- Usado em Fast Ethernet
- Reduz frequência do sinal

---

## 🔹 4D-PAM5

- Usado em Gigabit Ethernet
- Usa múltiplos níveis

---

# 🔁 8. Codificação de Bloco

---

## 📌 Objetivo:

- Melhorar sincronização
- Evitar sequências longas de 0 ou 1

---

## 🔹 4B/5B

- 4 bits → 5 bits

---

## 🔹 8B/10B

- Mais eficiente

---

## 🎯 Importante:

👉 Sempre aumenta o número de bits transmitidos

---

# 🧠 9. RESOLVENDO SUA QUESTÃO (PASSO A PASSO)

---

## 📌 Dado:

- Banda = 250 MHz
- Codificação da figura

---

## 📌 Passo 1: Identificar codificação

Pelo desenho:

- Tem níveis +V, 0, -V  
    👉 Isso indica **multinível (não é NRZ simples)**

---

## 📌 Passo 2: identificar L

- 3 níveis → L = 3

---

## 📌 Passo 3: aplicar Nyquist

#### N = 2B log⁡2 L

Substituindo:

#### N = 2 . 250 . Log2 (3)
#### Log2 (3) ≈ 1.58
#### N ≈ 2 . 250 . 1.58
#### N ≈ 790 Mbps

---

## ✅ Resposta:

👉 **≈ 790 Mbps**