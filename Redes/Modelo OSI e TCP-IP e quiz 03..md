
# Redes de Computadores — Modelo OSI e TCP/IP

## Modelos de comunicação em rede

Existem dois modelos principais usados para explicar a comunicação entre computadores:

- **Modelo OSI**
    
- **Modelo TCP/IP**
    

Esses modelos dividem a comunicação em **camadas**, onde cada camada possui responsabilidades específicas.

---

# Modelo OSI

O **modelo OSI (Open Systems Interconnection)** possui **7 camadas**.

Ele foi criado para **padronizar a comunicação entre sistemas de rede diferentes**.

## Camadas do modelo OSI

|Camada|Nome|Função|
|---|---|---|
|7|Aplicação|Interface com o usuário|
|6|Apresentação|Formatação, compressão e criptografia|
|5|Sessão|Controle da sessão de comunicação|
|4|Transporte|Comunicação entre processos|
|3|Rede|Roteamento e endereçamento lógico|
|2|Enlace de dados|Comunicação entre dispositivos na mesma rede|
|1|Física|Transmissão de bits|

---

# Camada Física (Camada 1)

Função:

- transmitir **bits pelo meio físico**
    
- converter bits em **sinais elétricos ou eletromagnéticos**
    
- interagir diretamente com o **meio de transmissão**
    

Exemplos:

- cabos
    
- conectores
    
- ondas eletromagnéticas
    

Característica importante:

- **é a única camada que não adiciona cabeçalho aos dados**
    

---

# Camada de Enlace de Dados (Camada 2)

Função:

- comunicação entre dispositivos da **mesma rede**
    
- controle de erros
    
- controle de fluxo
    
- controle de acesso ao meio
    

Características importantes:

- usa **endereço físico (MAC)**
    
- **adiciona cabeçalho e trailer**
    

PDU dessa camada:

Frame (quadro)

---

# Camada de Rede (Camada 3)

Função:

- **roteamento**
    
- entrega de dados entre redes diferentes
    

Endereço utilizado:

Endereço IP (endereço lógico)

PDU dessa camada:

Pacote

---

# Camada de Transporte (Camada 4)

Função principal:

Entrega de dados entre processos finais

Funções importantes:

- **segmentação**
    
- **remontagem**
    
- controle de erro
    
- controle de fluxo
    

Protocolos conhecidos:

- TCP
    
- UDP
    

PDU:

Segmento

---

# Camada de Sessão (Camada 5)

Funções:

- iniciar sessões
    
- manter sessões
    
- finalizar sessões
    

Controla a **conexão lógica entre aplicações**.

---

# Camada de Apresentação (Camada 6)

Funções:

- formatação de dados
    
- compressão
    
- criptografia
    
- conversão de formatos
    

Ela garante que **os dados sejam compreensíveis para a aplicação**.

---

# Camada de Aplicação (Camada 7)

É a camada **mais próxima do usuário**.

Fornece serviços como:

- correio eletrônico
    
- transferência de arquivos
    
- terminal remoto
    
- navegação na web
    

---

# Resumo das camadas:

### FÍSICA: é o fio da tomada (ela transporta bits (0 e 1) como sinais elétricos ou ondas).

### ENLACE: garante que os dados vão de um dispositivo ao outro dentro da mesma rede.

### REDE: é o waze. Define o caminho que os dados vão seguir. Podendo entregar dados entre redes diferentes.

### Transporte: garante que os dados chegarão completos em um dispositivo (podendo mandar de novo, se precisar). 

### Sessão: Cria, mantém e encerra conexões (Login em sites).

### Apresentação: traduz e formata os dados.

### Aplicação: camada que faz a conexão entre o programa e a rede.


---
# Modelo TCP/IP

O modelo **TCP/IP possui 4 camadas**.

|TCP/IP|OSI equivalente|
|---|---|
|Aplicação|Aplicação + Apresentação + Sessão|
|Transporte|Transporte|
|Internet|Rede|
|Acesso à rede|Enlace + Física|

---

# Encapsulamento

Quando dados são enviados:

Aplicação → Transporte → Rede → Enlace → Física

Cada camada **adiciona um cabeçalho**.

Isso é chamado:

Encapsulamento

Quando os dados chegam ao destino:

Física → Enlace → Rede → Transporte → Aplicação

Os cabeçalhos são **removidos**.

---

# PDU (Protocol Data Unit)

Cada camada possui uma **unidade de dados específica**.

|Camada|PDU|
|---|---|
|Aplicação|Dados|
|Transporte|Segmento|
|Rede|Pacote|
|Enlace|Frame|
|Física|Bits|

---

# Tipos de endereços em redes

## Endereço físico

Também chamado de:

MAC Address

Características:

- gravado na placa de rede
    
- usado na camada **enlace**
    

---

## Endereço lógico

Exemplo:

Endereço IP

Usado para:

- identificar dispositivos na rede
    

Camada:

Rede

---

## Endereço de porta

Identifica **processos dentro do computador**.

Exemplo:

Porta 80 → HTTP  
Porta 25 → SMTP

Camada:

Transporte

---

## Endereço específico

Endereço usado pela aplicação.

Exemplo:

www.google.com.br

Chamado de:

URL

Camada:

Aplicação

---

# Mudança de endereços entre redes

Quando um pacote atravessa redes diferentes:

- **Endereço lógico (IP)** → permanece o mesmo
    
- **Endereço físico (MAC)** → muda
    

Isso ocorre porque cada rede possui **interfaces físicas diferentes**.

---

# Perguntas e Respostas

## 1. Os serviços de correio eletrônico estão disponíveis para usuários da rede em qual camada?

Resposta: **Aplicação**

---

## 2. Qual camada é a única que acrescenta cabeçalho e trailer aos dados?

Resposta: **Camada de enlace de dados**

---

## 3. Quantas camadas possui o modelo TCP/IP?

Resposta: **4 camadas**

---

## 4. O que acontece com os cabeçalhos quando os pacotes sobem para camadas superiores?

Resposta: **Os cabeçalhos são removidos**

---

## 5. O endereço IP atribuído a um host é um exemplo de qual tipo de endereço?

Resposta: **Endereço lógico**

---

## 6. O endereço MAC de um adaptador de rede é exemplo de qual endereço?

Resposta: **Endereço físico**

---

## 7. A camada física adequa uma cadeia de quê ao meio físico?

Resposta: **Bits**

---

## 8. Qual camada converte bits em sinais eletromagnéticos?

Resposta: **Camada física**

---

## 9. O endereço específico é inserido no cabeçalho de qual camada?

Resposta: **Camada de aplicação**

---

## 10. Qual é a camada 1 do modelo OSI?

Resposta: **Camada física**

---

## 11. Qual é a camada 4 do modelo OSI?

Resposta: **Camada de transporte**

---

## 12. O endereço lógico é inserido no cabeçalho de qual camada?

Resposta: **Camada de rede**

---

## 13. Qual é o PDU da camada de rede?

Resposta: **Pacote**

---

## 14. Segmentação e remontagem são funções de qual camada?

Resposta: **Camada de transporte**

---

## 15. Quantas camadas possui o modelo OSI?

Resposta: **7 camadas**

---

## 16. Qual serviço é realizado pela camada de aplicação?

Resposta: **Todas as anteriores**

---

## 17. Qual camada fica entre rede e aplicação?

Resposta: **Transporte**

---

## 18. Qual é a principal função da camada de transporte?

Resposta: **Entrega de dados entre processos finais**

---

## 19. Qual é a camada 5 do modelo OSI?

Resposta: **Camada de sessão**

---

## 20. O endereço físico é inserido no cabeçalho de qual camada?

Resposta: **Camada de enlace de dados**

---

## 21. O endereço de porta pertence a qual camada?

Resposta: **Camada de transporte**

---

## 22. A URL [www.google.com.br](http://www.google.com.br) é exemplo de qual endereço?

Resposta: **Endereço específico**

---

## 23. Quando um pacote passa entre LANs diferentes, qual endereço muda e qual permanece?

Resposta:

Endereço físico muda  
Endereço lógico permanece

---

## 24. Qual é o PDU da camada de transporte?

Resposta: **Segmento**

---

## 25. Qual alternativa está correta sobre PDU de rede?

Resposta:

PDU de rede = Cabeçalho de rede + PDU de transporte

---

## 26. Qual é a camada 3 do modelo OSI?

Resposta: **Camada de rede**

---

## 27. A camada 2 fica entre quais camadas?

Resposta:

Entre a camada física e a camada de rede

---

## 28. O que significa a sigla PDU?

Resposta:

Unidade de Dados de Protocolo

---

## 29. Qual é a camada 2 do modelo OSI?

Resposta: **Camada de enlace de dados**

---

## 30. Qual camada interage diretamente com o meio de transmissão?

Resposta: **Camada física**

---

## 31. O que acontece com cabeçalhos quando os dados descem pelas camadas?

Resposta: **São adicionados**

---

## 32. A entrega de mensagens entre processos é responsabilidade de qual camada?

Resposta: **Camada de transporte**

---

## 33. Qual é a camada 6 do modelo OSI?

Resposta: **Camada de apresentação**

---

## 34. Qual é a camada 7 do modelo OSI?

Resposta: **Camada de aplicação**

---

## 35. Qual camada não adiciona cabeçalho aos dados?

Resposta: **Camada física**

---

## 36. Qual é o PDU da camada de enlace de dados?

Resposta: **Frame (quadro)**

---

## 37. O cabeçalho da camada 4 de A é lido por qual camada em B?

Resposta: **Camada de transporte**