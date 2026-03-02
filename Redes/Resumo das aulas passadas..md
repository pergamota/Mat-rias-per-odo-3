
# 1️⃣ Comunicação de Dados

## 📌 Definição

Comunicação de dados é a troca de informações entre dispositivos por meio de um meio de transmissão, seguindo regras chamadas protocolos.

---

## 📌 Componentes da Comunicação

1. Mensagem
    
2. Emissor
    
3. Receptor
    
4. Meio de transmissão
    
5. Protocolo
    

Sem protocolo, não há entendimento entre dispositivos.

---

## 📌 Fluxo de Dados

- **Simplex** → transmissão em um único sentido.
    
- **Half-duplex** → transmissão nos dois sentidos, mas alternadamente.
    
- **Full-duplex** → transmissão simultânea nos dois sentidos.
    

---

## 📌 Eficácia de um Sistema

Um sistema eficiente precisa ter:

- **Entrega correta**
    
- **Precisão**
    
- **Sincronização**
    
- **Jitter baixo** (variação no tempo de chegada dos pacotes — muito importante em vídeo ao vivo)
    

---

# 2️⃣ Redes de Computadores

## 📌 Definição

Rede é um conjunto de dispositivos (nós) interligados por enlaces de comunicação.

---

## 📌 Critérios de uma Rede

### 🔹 Desempenho

- Throughput (vazão)
    
- Delay (atraso)
    

### 🔹 Confiabilidade

- Frequência de falhas
    
- Tempo de recuperação
    
- Robustez
    

### 🔹 Segurança

- Proteção contra acesso indevido
    
- Proteção contra perda ou alteração de dados
    

---

# 3️⃣ Categorias de Redes

## 🔹 LAN (Local Area Network)

Rede de pequena área (casa, escola, empresa).

## 🔹 MAN (Metropolitan Area Network)

Rede que cobre uma cidade.

## 🔹 WAN (Wide Area Network)

Rede de longa distância (país, continente ou mundo).

A internet é uma WAN.

---

# 4️⃣ Protocolos

Protocolo é um conjunto de regras que define como ocorre a comunicação.

Ele possui três elementos:

- **Sintaxe** → formato dos dados
    
- **Semântica** → significado dos dados
    
- **Timing** → quando e com que velocidade enviar
    

---

# 5️⃣ Modelo OSI

Criado pela ISO.

Possui 7 camadas:

1. Física
    
2. Enlace de Dados
    
3. Rede
    
4. Transporte
    
5. Sessão
    
6. Apresentação
    
7. Aplicação
    

---

## 📌 Função das Camadas Principais

### 🔹 Física

Transmite bits.

### 🔹 Enlace

Entrega quadros entre nós vizinhos.  
Controla erros locais e usa endereço físico.

### 🔹 Rede

Entrega pacotes da origem ao destino.  
Usa endereço lógico (IP).  
Faz roteamento.

### 🔹 Transporte

Entrega confiável de processo para processo.  
Usa endereço de porta.  
Faz controle de fluxo e erro fim-a-fim.

## 🔹 5. Sessão

Controla o diálogo.

## 🔹 6. Apresentação

- Tradução
    
- Compressão
    
- Criptografia

## 🔹 7. Aplicação

Interface com o usuário.

Exemplos:

- Telnet
    
- Email
    
- Transferência de arquivos
    
- Diretórios

---

# 6️⃣ Encapsulamento

Encapsulamento é o processo no qual cada camada adiciona seu próprio cabeçalho aos dados antes de enviá-los para a camada inferior.

No destino, ocorre o desencapsulamento (remoção dos cabeçalhos).

### 📌 PDU (Protocol Data Unit)

PDU = Cabeçalho da camada + dados recebidos da camada superior.

Cada camada tem sua própria PDU.

---

# 7️⃣ Roteamento

Roteamento é a função da camada de Rede.

É o processo de escolher o melhor caminho para que um pacote chegue ao destino final.

---

# 8️⃣ Endereçamento no TCP/IP

Existem quatro tipos de endereços:

---

## 🔹 Endereço Físico (MAC)

- 48 bits
    
- Usado na camada de enlace
    
- Muda a cada salto
    

---

## 🔹 Endereço Lógico (IP)

- Usado na camada de rede
    
- Permanece do início ao fim
    
- Identifica o dispositivo na internet
    

---

## 🔹 Endereço de Porta

- 16 bits
    
- Identifica o processo dentro do computador
    
- Permanece do início ao fim
    

---

## 🔹 Endereço Específico

Exemplos:

- E-mail
    
- URL
    
- Nome de máquina
    

É o que o usuário digita.

---

# 9️⃣ Modelo TCP/IP

Possui 4 ou 5 camadas:

- Física
    
- Enlace
    
- Rede
    
- Transporte
    
- Aplicação
    

Não corresponde exatamente ao modelo OSI.

---

# 🔟 Conceitos-Chave que Sempre Caem em Prova

✔ Endereço físico muda a cada salto  
✔ Endereço lógico não muda  
✔ Porta identifica processo  
✔ Encapsulamento = adição de cabeçalhos  
✔ Roteamento é função da camada de rede  
✔ Jitter é variação no atraso  
✔ Transporte garante entrega confiável  
✔ LAN < MAN < WAN