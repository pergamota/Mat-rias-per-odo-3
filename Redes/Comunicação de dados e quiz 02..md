
## 1. O que é comunicação de dados

Comunicação de dados é o **processo de troca de informações entre dois ou mais dispositivos** através de algum meio de transmissão.

Para que essa comunicação aconteça, são necessários **cinco elementos principais**:

1. **Mensagem** → informação que será transmitida
    
2. **Emissor** → dispositivo que envia a mensagem
    
3. **Receptor** → dispositivo que recebe a mensagem
    
4. **Meio de transmissão** → caminho físico por onde o sinal passa
    
5. **Protocolo** → conjunto de regras que controla a comunicação
    

Exemplo simples:

Computador → envia mensagem → internet → outro computador

---

# 2. Mensagem

A **mensagem** é a **informação que será transmitida**.

Ela pode ser:

- texto
    
- números
    
- imagens
    
- áudio
    
- vídeo
    
- arquivos
    

Ou seja, qualquer tipo de **dado digital ou analógico**.

---

# 3. Meio de transmissão

O **meio** é o **caminho físico por onde a informação viaja**.

Ele transporta o **sinal que carrega os dados**.

Tipos de meios:

### Meios guiados (com fio)

- cabo de cobre
    
- cabo coaxial
    
- fibra óptica
    

### Meios não guiados (sem fio)

- ondas de rádio
    
- Wi-Fi
    
- satélite
    
- micro-ondas
    

Exemplo:  
Um cabo de rede Ethernet é um **meio físico de transmissão**.

---

# 4. Protocolos de comunicação

Um **protocolo** é um **conjunto de regras que define como os dispositivos se comunicam**.

Essas regras determinam:

- formato dos dados
    
- significado das mensagens
    
- momento de envio
    
- velocidade de transmissão
    

Exemplo de protocolos:

- HTTP
    
- TCP
    
- IP
    
- FTP
    
- SMTP
    

---

# 5. Três elementos de um protocolo

Todo protocolo possui **três componentes fundamentais**.

## 1️⃣ Sintaxe

A **sintaxe** define o **formato da mensagem**.

Ou seja:

- estrutura dos dados
    
- ordem dos campos
    
- tamanho das informações
    

Exemplo:

Um endereço IPv4 possui:

- **32 bits**
    
- dividido em **4 números**
    
- cada número varia de **0 a 255**
    

Exemplo de IP:

192.168.1.2

Isso é uma **regra de sintaxe**.

---

## 2️⃣ Semântica

A **semântica** define **o significado dos dados**.

Ou seja:

- o que cada campo representa
    
- qual informação cada parte da mensagem contém
    

Exemplo:

Um campo pode indicar:

- tipo de mensagem
    
- confirmação de recebimento
    
- controle de erro
    

---

## 3️⃣ Timing

O **timing** define **quando os dados devem ser enviados e com que velocidade**.

Ele determina:

- a ordem de envio
    
- a sincronização
    
- a taxa de transmissão
    

---

# 6. Tipos de transmissão de dados

A comunicação entre dispositivos pode ocorrer de **três formas principais**.

---

## Simplex

Na transmissão **simplex**, os dados circulam **apenas em uma direção**.

Um dispositivo **somente envia** e o outro **somente recebe**.

Exemplo:

**TV analógica**

A televisão transmite sinal, mas o usuário não responde.

Outro exemplo:

**Teclado → computador**

O teclado envia dados, mas não recebe.

---

## Half-duplex

Na transmissão **half-duplex**, os dispositivos **podem enviar e receber**, porém **não ao mesmo tempo**.

A comunicação ocorre **em turnos**.

Exemplo:

**rádio comunicador (walkie-talkie)**

Uma pessoa fala enquanto a outra espera.

---

## Full-duplex

Na transmissão **full-duplex**, os dispositivos **transmitem e recebem ao mesmo tempo**.

Exemplo:

 **telefone**

As duas pessoas falam e escutam simultaneamente.

---

# 7. Aplicações sensíveis a atraso

Na Internet, algumas aplicações são mais sensíveis a **atrasos (delay)**.

## Delay

É o **tempo que o dado leva para sair do emissor até chegar ao receptor**.

Aplicações pouco sensíveis a atraso:

- enviar email
    
- download de arquivos
    
- navegação simples
    

Aplicações **muito sensíveis a atraso**:

- chamadas de vídeo
    
- chamadas de voz
    
- videoconferência
    
- Skype ou Zoom
    

Se houver atraso grande, a conversa fica **travada**.

---

# 8. Jitter

O **jitter** é a **variação do atraso entre pacotes de dados**.

Exemplo:

Um pacote chega em 20 ms  
Outro chega em 60 ms  
Outro em 10 ms

Essa variação causa:

- cortes de áudio
    
- vídeo travando
    
- voz robótica
    

Aplicações mais sensíveis ao jitter:

- chamadas de voz
    
- chamadas de vídeo
    
- VoIP (Skype, Discord)
    

---

# 9. Características importantes de uma rede

## Desempenho

O **desempenho** mede a eficiência da rede.

Ele depende de fatores como:

- velocidade de transmissão
    
- número de usuários
    
- hardware
    
- software
    
- largura de banda
    

---

## Confiabilidade

A **confiabilidade** mede a **frequência de falhas da rede**.

Ela também considera:

- quanto tempo a rede fica fora do ar
    
- quanto tempo demora para se recuperar
    

Ou seja:

Confiabilidade envolve:

- frequência de falhas
    
- tempo de recuperação
    
- estabilidade da rede
    

---

## Segurança

A **segurança da rede** protege os dados e sistemas contra acesso não autorizado.

Ela envolve:

- controle de acesso
    
- criptografia
    
- autenticação
    
- proteção contra invasões
    

Exemplo:

Um **usuário não autorizado** acessando a rede é um **problema de segurança**.

---

# 10. Tipos de redes

As redes podem ser classificadas pelo **tamanho da área coberta**.

---

## LAN (Local Area Network)

Rede local que cobre uma **pequena área**.

Exemplo:

- casa
    
- escritório
    
- escola
    
- laboratório
    

Um exemplo de LAN:

Dois computadores conectados por um **roteador Wi-Fi em casa**.

---

## MAN (Metropolitan Area Network)

Rede que cobre **uma cidade**.

Exemplo:

redes de operadoras de internet em uma cidade.

---

## WAN (Wide Area Network)

Rede que cobre **grandes distâncias**.

Exemplo:

 **Internet**

Ela conecta redes do mundo inteiro.

---

# 11. Organizações que padronizam redes

Existem organizações responsáveis por criar **padrões de comunicação**.

Uma das mais importantes é a:

**ITU-T (International Telecommunication Union – Telecommunication Standardization Sector)**.

Ela regula e padroniza **comunicações nacionais e internacionais**.

Outras organizações importantes:

- **IEEE** → padrões de redes (ex: Wi-Fi)
    
- **ISO** → padrões internacionais
    
- **FCC** → regula telecomunicações nos EUA
  
 
### 1. Frequência de falhas e tempo de recuperação da rede pós falha são medidas da:

✅ **Confiabilidade**

---

### 2. Em um protocolo, a estrutura ou formato dos dados refere-se à:

✅ **Sintaxe**

---

### 3. Em um protocolo, o que define quando os dados devem ser enviados e com que rapidez:

✅ **Timing**

---

### 4. A informação a ser trocada num sistema de comunicação de dados recebe o nome de:

✅ **Mensagem**

---

### 5. A regra do formato do endereço IPv4 refere-se à:

✅ **Sintaxe**

---

### 6. Na transmissão em que cada parte pode transmitir ou receber informações:

✅ **Half-duplex**

(podem enviar e receber, mas não ao mesmo tempo)

---

### 7. Aplicação mais sensível a atrasos (delay):

✅ **Conversar via Skype**

---

### 8. Em um protocolo, o significado de cada seção de bits refere-se à:

✅ **Semântica**

---

### 9. A transmissão de TV analógica é um exemplo de:

✅ **Simplex**

---

### 10. Na transmissão em que os dois lados transmitem e recebem simultaneamente:

✅ **Full-duplex**

---

### 11. Organização com autoridade sobre o comércio nacional e internacional no campo das comunicações:

✅ **ITU-T**

---

### 12. Um usuário não autorizado é um problema de:

✅ **Segurança**

---

### 13. Dois computadores conectados à Internet em casa por um roteador sem fio é exemplo de:

✅ **LAN**

---

### 14. Aplicação mais sensível à variação de atraso (jitter):

✅ **Conversar via Skype**

---

### 15. O caminho físico por onde passa a informação é o:

✅ **Meio**

---

### 16. A comunicação entre um computador e um teclado envolve transmissão:

✅ **Simplex**

(teclado envia dados, mas não recebe) 
  