

# EXPLICAÇÃO DETALHADA POR TÓPICO

## 1. MODELOS DE BANCO DE DADOS

### Modelo Relacional

- **O que é**: organiza dados em **tabelas** com linhas e colunas.
    
- **Quando usar**: quando há relações bem definidas entre os dados.
    
- **Exemplo da tarefa**: `Cliente` e `Conta` – um cliente pode ter várias contas, uma conta pode ter vários clientes.
    
- **Características**: usa chaves primárias e estrangeiras.
    

### Modelo Não Relacional (NoSQL)

- **O que é**: documentos flexíveis, sem esquema fixo.
    
- **Quando usar**: quando os dados podem ter estruturas diferentes.
    
- **Exemplo da tarefa**: sistema de gerenciamento de documentos distribuídos.
    
- **Características**: cada documento pode ser diferente do outro.
    

### Modelo Hierárquico

- **O que é**: estrutura em árvore, como um organograma.
    
- **Quando usar**: quando cada elemento tem um único "pai".
    
- **Exemplo da tarefa**: estrutura organizacional de uma empresa (gerente → funcionários).
    

---

## 2. RESTRIÇÕES DE INTEGRIDADE 

**O que são**: regras que garantem que os dados do banco sejam **confiáveis** e **consistentes**.

### Principais tipos:

|Restrição|O que faz|Exemplo|
|---|---|---|
|**Chave primária (PK)**|Garante que cada linha seja única|`id_aluno` não pode se repetir|
|**Chave estrangeira (FK)**|Garante que um valor existe em outra tabela|O `id_curso` do aluno deve existir na tabela Curso|
|**NOT NULL**|Impede valores vazios|`nome` não pode ficar em branco|
|**UNIQUE**|Garante valores únicos|`CPF` não pode se repetir|
|**CHECK**|Valida uma condição|`idade >= 18`|

**Por que garantem confiabilidade?**

- Evitam dados duplicados
    
- Impedem registros "órfãos" (que referenciam algo que não existe)
    
- Mantêm a integridade referencial
    

---

## 3. ENTIDADES, ATRIBUTOS E RELACIONAMENTOS

### Entidade

- É um "objeto" do mundo real que tem existência própria.
    
- **Exemplo da tarefa**: `Faculdade`, `Aluno`
    

### Atributos

- São as características da entidade.
    
- **Exemplo da tarefa**:
    
    - Faculdade: `código do curso`, `nome do curso`
        
    - Aluno: `matrícula`, `nome`, `endereço` (que pode ser composto: `rua`, `número`, `bairro`)
        

### Relacionamento

- É a ligação entre entidades.
    
- **Exemplo da tarefa**: `matrícula` (liga Aluno a Faculdade)
    

---

## 4. GENERALIZAÇÃO E ESPECIALIZAÇÃO

### O que é

- **Generalização**: juntar entidades com características comuns em uma entidade mais genérica.
    
- **Especialização**: dividir uma entidade genérica em subcategorias.
    

### Exemplo da tarefa

- **Entidade genérica**: `Carro`
    
- **Entidades específicas**: `City` e `Civic` (são tipos específicos de carro)
    

**Diagrama:**

text

      Carro (genérico)
       /    \
   City     Civic (específicos)

---

## 5. MODELO LÓGICO 

### O que é

- É a tradução do diagrama ER (Entidades e Relacionamentos) para **tabelas** com chaves.
    

### Exemplo da tarefa (biblioteca)

sql

-- Tabela Estante
Estante (id_estante PK, nome)

-- Tabela Autor  
Autor (id_autor PK, nome)

-- Tabela Livro
Livro (codigo PK, titulo, ano, id_estante FK, id_editora FK)

-- Tabela associativa (N:N entre Livro e Autor)
Livro_Autor (codigo_livro PK FK, id_autor PK FK)

-- Tabela Empréstimo (chave composta)
Emprestimo (id_aluno PK FK, codigo_livro PK FK, data_emprestimo PK, data_devolucao)

**Observação**: empréstimo tem chave composta por `(id_aluno, codigo_livro, data_emprestimo)` porque um aluno pode pegar o mesmo livro em datas diferentes.


# O QUE É NORMALIZAÇÃO?

Normalização é o processo de **organizar os dados** para evitar:

- **Redundância** (dados repetidos)
    
- **Anomalias** (problemas ao inserir, atualizar ou deletar)
    

**Anomalias na prática:**

- **Inserção**: não consigo cadastrar um autor sem um livro
    
- **Atualização**: preciso mudar o nome do autor em 50 lugares
    
- **Exclusão**: ao deletar um livro, perco o autor junto
    

---

# 🔵 1ª FORMA NORMAL (1FN)

## 🎯 OBJETIVO

Eliminar **atributos multivalorados** e **atributos compostos**. Cada célula deve conter **um único valor atômico**.

## ❌ PROBLEMA (Tabela violando 1FN)

Imagine uma tabela de **PEDIDOS**:

|ID_Pedido|Cliente|Telefones|Produtos|Quantidades|Valor_Total|
|---|---|---|---|---|---|
|1|João Silva|(11)99999-1111, (11)88888-2222|Camisa, Calça, Sapato|2, 1, 1|450,00|
|2|Maria Souza|(11)77777-3333|Camisa|3|150,00|
|3|Pedro Lima|(11)66666-4444, (11)55555-5555|Calça, Blusa|2, 2|320,00|

### 🔍 O QUE ESTÁ ERRADO?

1. **Telefones**: tem **dois valores** na mesma célula (multivalorado)
    
2. **Produtos**: vários produtos em uma célula (multivalorado)
    
3. **Quantidades**: várias quantidades em uma célula (multivalorado)
    

### ⚠️ ANOMALIAS QUE ISSO CAUSA

- **Inserção**: como adicionar um telefone novo sem repetir o pedido todo?
    
- **Atualização**: se o cliente mudar o telefone, preciso alterar em vários lugares
    
- **Consulta**: como buscar "todos os pedidos com Camisa"? Difícil e lento
    

---

## ✅ SOLUÇÃO - PASSO A PASSO PARA 1FN

### PASSO 1: Identificar atributos multivalorados

- `Telefones` → pode ter vários telefones
    
- `Produtos` → pode ter vários produtos
    
- `Quantidades` → cada produto tem uma quantidade
    

### PASSO 2: Criar tabelas separadas para cada atributo multivalorado

**Tabela 1: PEDIDO** (dados fixos do pedido)

|ID_Pedido|Cliente|Valor_Total|
|---|---|---|
|1|João Silva|450,00|
|2|Maria Souza|150,00|
|3|Pedro Lima|320,00|

**Tabela 2: TELEFONE_CLIENTE** (telefones do cliente)

|ID_Pedido|Telefone|
|---|---|
|1|(11)99999-1111|
|1|(11)88888-2222|
|3|(11)66666-4444|
|3|(11)55555-5555|

**Tabela 3: ITEM_PEDIDO** (produtos de cada pedido)

|ID_Pedido|Produto|Quantidade|
|---|---|---|
|1|Camisa|2|
|1|Calça|1|
|1|Sapato|1|
|2|Camisa|3|
|3|Calça|2|
|3|Blusa|2|

### ✅ RESULTADO APÓS 1FN

- Cada célula tem **apenas um valor**
    
- Não há mais atributos multivalorados
    
- Agora podemos consultar facilmente
    

---

# 2ª FORMA NORMAL (2FN)

## OBJETIVO

Eliminar **dependências parciais**. Isso só se aplica quando a **chave primária é composta** (mais de uma coluna).

## REGRA DA 2FN

1. Estar na **1FN**
    
2. **Todos os atributos não-chave** devem depender da **chave primária COMPLETA**, não apenas de uma parte dela
    

## PROBLEMA (Tabela violando 2FN)

Após aplicar a 1FN, temos a tabela `ITEM_PEDIDO`. Mas vamos adicionar mais informações:

|ID_Pedido|ID_Produto|Quantidade|Nome_Produto|Preco_Unitario|Categoria|
|---|---|---|---|---|---|
|1|P001|2|Camisa Polo|50,00|Vestuário|
|1|P002|1|Calça Jeans|120,00|Vestuário|
|1|P003|1|Sapato Social|200,00|Calçados|
|2|P001|3|Camisa Polo|50,00|Vestuário|
|3|P002|2|Calça Jeans|120,00|Vestuário|
|3|P004|2|Blusa Feminina|60,00|Vestuário|

### QUAL É A CHAVE PRIMÁRIA?

- `(ID_Pedido, ID_Produto)` → **chave composta** (precisa dos dois para identificar unicamente)
    

### O QUE ESTÁ ERRADO?

Vamos analisar cada atributo:

|Atributo|Depende de|É dependência parcial?|
|---|---|---|
|`Quantidade`|`(ID_Pedido + ID_Produto)`|❌ NÃO (depende da chave completa)|
|`Nome_Produto`|`ID_Produto` APENAS|✅ SIM (dependência parcial)|
|`Preco_Unitario`|`ID_Produto` APENAS|✅ SIM (dependência parcial)|
|`Categoria`|`ID_Produto` APENAS|✅ SIM (dependência parcial)|

### ANOMALIAS QUE ISSO CAUSA

**Anomalia de atualização:**

- Se o preço da Camisa Polo mudar de R$50,00 para R$55,00, preciso atualizar em **todas as linhas** onde aparece (linhas 1 e 5)
    

**Anomalia de inserção:**

- Não consigo cadastrar um novo produto (ex: "Tênis Esportivo") sem associá-lo a um pedido
    

**Anomalia de exclusão:**

- Se eu deletar o último pedido que contém "Camisa Polo", perco os dados da Camisa Polo
    

---

## SOLUÇÃO - PASSO A PASSO PARA 2FN

### PASSO 1: Identificar a chave primária composta

Chave = `(ID_Pedido, ID_Produto)`

### PASSO 2: Identificar quais atributos dependem de PARTE da chave

- Atributos que dependem de `ID_Produto`: `Nome_Produto`, `Preco_Unitario`, `Categoria`
    
- Atributos que dependem de `ID_Pedido` (se houvesse): neste exemplo não tem
    

### PASSO 3: Criar tabelas separadas

**Tabela 1: PRODUTO** (dados que dependem apenas do produto)

|ID_Produto (PK)|Nome_Produto|Preco_Unitario|Categoria|
|---|---|---|---|
|P001|Camisa Polo|50,00|Vestuário|
|P002|Calça Jeans|120,00|Vestuário|
|P003|Sapato Social|200,00|Calçados|
|P004|Blusa Feminina|60,00|Vestuário|

**Tabela 2: ITEM_PEDIDO** (dados que dependem da chave COMPLETA)

|ID_Pedido (PK FK)|ID_Produto (PK FK)|Quantidade|
|---|---|---|
|1|P001|2|
|1|P002|1|
|1|P003|1|
|2|P001|3|
|3|P002|2|
|3|P004|2|

**Tabela 3: PEDIDO** (mantida da 1FN)

|ID_Pedido (PK)|Cliente|Valor_Total|
|---|---|---|
|1|João Silva|450,00|
|2|Maria Souza|150,00|
|3|Pedro Lima|320,00|

### RESULTADO APÓS 2FN

- Cada atributo não-chave depende da chave completa
    
- Produtos podem ser cadastrados independentemente
    
- Preço do produto é atualizado em um único lugar
    

---

# 3ª FORMA NORMAL (3FN)

## OBJETIVO

Eliminar **dependências transitivas**. Ou seja, um atributo não-chave **não pode depender de outro atributo não-chave**.

## REGRA DA 3FN

1. Estar na **2FN**
    
2. **Nenhum atributo não-chave** pode depender de **outro atributo não-chave** (todos devem depender **apenas** da chave primária)
    

## PROBLEMA (Tabela violando 3FN)

Vamos expandir nossa tabela de **PEDIDO**:

|ID_Pedido (PK)|ID_Cliente|Nome_Cliente|Cidade_Cliente|UF_Cliente|Data_Pedido|Valor_Total|
|---|---|---|---|---|---|---|
|1|C001|João Silva|São Paulo|SP|15/03/2025|450,00|
|2|C002|Maria Souza|Rio de Janeiro|RJ|16/03/2025|150,00|
|3|C003|Pedro Lima|São Paulo|SP|16/03/2025|320,00|
|4|C001|João Silva|São Paulo|SP|17/03/2025|280,00|

### ANALISANDO AS DEPENDÊNCIAS

|Atributo|Depende de|É dependência direta da PK?|
|---|---|---|
|`ID_Cliente`|`ID_Pedido`|✅ SIM (chave estrangeira)|
|`Nome_Cliente`|`ID_Cliente`|❌ NÃO (depende de outro não-chave)|
|`Cidade_Cliente`|`ID_Cliente`|❌ NÃO (depende de outro não-chave)|
|`UF_Cliente`|`ID_Cliente`|❌ NÃO (depende de outro não-chave)|
|`Data_Pedido`|`ID_Pedido`|✅ SIM|
|`Valor_Total`|`ID_Pedido`|✅ SIM|

### O QUE É UMA DEPENDÊNCIA TRANSITIVA?

É quando: `Chave Primária → Atributo A → Atributo B`

No nosso caso:

- `ID_Pedido → ID_Cliente → Nome_Cliente`
    
- `ID_Pedido → ID_Cliente → Cidade_Cliente`
    
- `ID_Pedido → ID_Cliente → UF_Cliente`
    

O `Nome_Cliente` não depende diretamente do `ID_Pedido`, ele depende do `ID_Cliente`.

### ANOMALIAS QUE ISSO CAUSA

**Anomalia de atualização:**

- Se o João Silva se mudar para Campinas, preciso atualizar `Cidade_Cliente` em **todos os pedidos** dele (linhas 1 e 4)
    

**Anomalia de inserção:**

- Não consigo cadastrar um novo cliente sem ele ter feito um pedido
    

**Anomalia de exclusão:**

- Se eu deletar o único pedido do Pedro Lima, perco todos os dados dele
    

---

## SOLUÇÃO - PASSO A PASSO PARA 3FN

### PASSO 1: Identificar dependências transitivas

- `Nome_Cliente` depende de `ID_Cliente`, não de `ID_Pedido`
    
- `Cidade_Cliente` depende de `ID_Cliente`
    
- `UF_Cliente` depende de `ID_Cliente`
    

### PASSO 2: Criar tabela separada para os dados que causam dependência transitiva

**Tabela 1: CLIENTE** (dados que dependem do cliente)

|ID_Cliente (PK)|Nome_Cliente|Cidade_Cliente|UF_Cliente|
|---|---|---|---|
|C001|João Silva|São Paulo|SP|
|C002|Maria Souza|Rio de Janeiro|RJ|
|C003|Pedro Lima|São Paulo|SP|

**Tabela 2: PEDIDO** (com apenas a referência ao cliente)

|ID_Pedido (PK)|ID_Cliente (FK)|Data_Pedido|Valor_Total|
|---|---|---|---|
|1|C001|15/03/2025|450,00|
|2|C002|16/03/2025|150,00|
|3|C003|16/03/2025|320,00|
|4|C001|17/03/2025|280,00|

### RESULTADO APÓS 3FN

- Não há dependências transitivas
    
- Cliente pode ser cadastrado independentemente
    
- Dados do cliente são atualizados em um único lugar
    

---

# RESUMO COMPLETO - TABELA COMPARATIVA

|Forma Normal|Regra|Problema que Resolve|Ação Necessária|
|---|---|---|---|
|**1FN**|Cada célula = 1 valor atômico|Atributos multivalorados|Criar novas tabelas para os atributos multivalorados|
|**2FN**|Atributos não-chave dependem da chave COMPLETA|Dependências parciais (só em chave composta)|Separar atributos que dependem de parte da chave|
|**3FN**|Atributos não-chave dependem SOMENTE da chave|Dependências transitivas|Separar atributos que dependem de outros não-chave|

---

# EXEMPLO COMPLETO - DO INÍCIO AO FIM

Vamos normalizar uma tabela de **MATRÍCULA ESCOLAR**:

### TABELA ORIGINAL (FORMA 0)

|CPF_Aluno|Nome_Aluno|Telefones|Cod_Curso|Nome_Curso|Carga_Horaria|Cod_Disciplina|Nome_Disciplina|Nota|
|---|---|---|---|---|---|---|---|---|
|111|João|9999, 8888|C001|Engenharia|4000|D001|Cálculo|8.5|
|111|João|9999, 8888|C001|Engenharia|4000|D002|Física|7.0|
|222|Maria|7777|C001|Engenharia|4000|D001|Cálculo|9.0|
|222|Maria|7777|C001|Engenharia|4000|D002|Física|8.0|
|333|Pedro|6666, 5555|C002|Direito|3600|D003|Civil|8.0|

### APÓS 1FN (eliminar multivalorados)

**Tabela ALUNO:**

|CPF_Aluno (PK)|Nome_Aluno|
|---|---|
|111|João|
|222|Maria|
|333|Pedro|

**Tabela TELEFONE_ALUNO:**

|CPF_Aluno (FK)|Telefone|
|---|---|
|111|9999|
|111|8888|
|222|7777|
|333|6666|
|333|5555|

**Tabela MATRÍCULA (ainda com problemas):**

|CPF_Aluno|Cod_Curso|Nome_Curso|Carga_Horaria|Cod_Disciplina|Nome_Disciplina|Nota|
|---|---|---|---|---|---|---|
|111|C001|Engenharia|4000|D001|Cálculo|8.5|
|111|C001|Engenharia|4000|D002|Física|7.0|
|222|C001|Engenharia|4000|D001|Cálculo|9.0|
|222|C001|Engenharia|4000|D002|Física|8.0|
|333|C002|Direito|3600|D003|Civil|8.0|

### APÓS 2FN (eliminar dependências parciais)

**Chave primária da MATRÍCULA**: `(CPF_Aluno, Cod_Disciplina)` → chave composta

Identificando dependências:

- `Nome_Curso` depende de `Cod_Curso` (parcial)
    
- `Carga_Horaria` depende de `Cod_Curso` (parcial)
    
- `Nome_Disciplina` depende de `Cod_Disciplina` (parcial)
    
- `Nota` depende da chave completa `(CPF_Aluno, Cod_Disciplina)`
    

**Tabela CURSO:**

|Cod_Curso (PK)|Nome_Curso|Carga_Horaria|
|---|---|---|
|C001|Engenharia|4000|
|C002|Direito|3600|

**Tabela DISCIPLINA:**

|Cod_Disciplina (PK)|Nome_Disciplina|
|---|---|
|D001|Cálculo|
|D002|Física|
|D003|Civil|

**Tabela MATRÍCULA (simplificada):**

|CPF_Aluno (FK)|Cod_Disciplina (FK)|Nota|
|---|---|---|
|111|D001|8.5|
|111|D002|7.0|
|222|D001|9.0|
|222|D002|8.0|
|333|D003|8.0|

### APÓS 3FN (eliminar dependências transitivas)

**Verificando se há dependências transitivas:**

Na tabela `MATRÍCULA`, temos:

- `CPF_Aluno` → dados do aluno estão em outra tabela (já separado) ✅
    

Na tabela `DISCIPLINA`:

- Não há dependência transitiva ✅
    

Na tabela `CURSO`:

- Não há dependência transitiva ✅
    

### **ESTRUTURA FINAL NORMALIZADA:**


ALUNO (CPF_Aluno PK, Nome_Aluno)
    ↓
TELEFONE_ALUNO (CPF_Aluno FK, Telefone PK)
	
CURSO (Cod_Curso PK, Nome_Curso, Carga_Horaria)
	
DISCIPLINA (Cod_Disciplina PK, Nome_Disciplina, Cod_Curso FK)
	
MATRÍCULA (CPF_Aluno FK, Cod_Disciplina FK, Nota) → PK composta
	