
# Modelagem de dados: é o processo de estruturar/organizar de forma eficiente os dados em um banco de dados.

### Modelagem Conceitual: representação abstrata dos dados.


### Modelagem Lógica: conversão do modelo conceitual para tabelas.


### Modelo Relacional: organiza os dados em tabelas com domínios, atributos, tuplas e relações.

* Domínios: conjunto de valores permitidos para um atributo.
* Atributos: características das colunas da tabela.
* Tuplas: registros individuais (linhas da tabela).
* Relações : conjuntos de tuplas armazenadas em uma tabela.
  
  
### Restrições do modelo relacional: 

Explícita: podem ser expressas diretamente nos esquemas do modelo de dados (desenhos/tabelas).

Implícita: baseadas na aplicação ou restrições semânticas (Exemplo: um atributo `gênero` em uma tabela de pessoas deve aceitar apenas valores como "masculino" ou "feminino", o que é uma restrição semântica) ou regras de negócio.


### Como as restrições garantem a confiabilidade do banco de dados?

[Como as restrições garantem a confiabilidade do banco de dados](https://pucdegoias-my.sharepoint.com/:w:/g/personal/20251002803166_pucgo_edu_br/IQB11Sj8nXzqR7OPhJzNwBe4AcKG77cBKrqTGaKkb_O62QY?e=Mld7Vo)


# Modelo Entidade - Relacionamento:

É uma representação gráfica dos dados e tudo que tem relação. Baseando-se em entidades, atributos e relacionamentos, assim, ajuda muito na estruturação do banco de dados e também facilita o design do banco de dados.


### Entidade: representa um objeto da vida real, por exemplo, um médico, um paciente... (No desenho é representado por um retângulo)

* Entidades fortes: possuem uma chave própria.
* Entidades fracas: precisam de outras entidades para existir.
  
### Atributo: são características de uma entidade. (No desenho é representado por uma elipse).


### Relacionamento: é uma associação entre as entidades. (Representado por um losango).



# TAREFA 5:

### Identifique entidades, atributos, relacionamentos para um sistema acadêmico:

Entidades: Faculdade e Aluno.

Atributos: código do curso, nome do curso, data, número, matrícula, nome, endereço, rua, número, bairro.

Relacionamento: matrícula.

### FOTO DO DESENHO


# Tarefa 6:

### Identifique uma entidade em um sistema real que possa ser generalizada ou especializada:

Sistema --> entidade genérica: carros. Entidade específica: city e civic.


### FOTO DO DESENHO



# Tarefa 7:

### FOTO DO DESENHO


Modelo lógico:


```
Estante (
	id_estante(PK)
	nome
)
```

```
Autor (
	id_autor(PK)
	nome
)
```

```
Livro (
	codigo (PK)  
	titulo  
	ano  
	id_estante (FK)  
	id_editora (FK)
)
```

```
Livro_autor (
	codigo_livro (FK)  
	id_autor (FK)    
	PK (codigo_livro, id_autor)
)
```

```
Emprestimo (
	id_aluno (FK)  
	codigo_livro (FK)  
	data_emprestimo  
	data_devolucao  
	PK (id_aluno, codigo_livro, data_emprestimo)
)
```


# Tarefa 8:

**Problema:**  
A coluna Produtos contém dois valores em uma única célula, violando a Primeira Forma Normal.

**Solução:**  
Dividir a tabela em duas tabelas relacionadas:

- Pedido
    
- Produto_Pedido
    

### COLOQUE A FOTO AQUI


**Vantagens:**

- elimina valores múltiplos em uma célula
    
- melhora organização do banco
    
- reduz redundância de dados


# Tarefa 9:

### Questão 1:

A chave primária é composta por CodServico e CodPeca, porque um serviço pode usar várias peças e uma mesma peça pode estar em diferentes serviços.

### Questão 2:

* Dependência 1: CodServico -> NomeServico (porque um código de serviço sempre tem um nome)

* Dependência 2: CodServico → DataServico (porque cada serviço tem uma data)

* Dependência 3: CodPeca → NomePeca (porque cada peça tem um nome)
  
* Dependência 4: CodPeca → PrecoUnitario (porque cada peça tem um preço)

* Dependência 5: CodServico + CodPeca → Quantidade (porque a quantidade depende do serviço e da peça usada nele)
  
  
### Questão 3: 

|Dependência|Tipo|
|---|---|
|CodServico → NomeServico|Parcial|
|CodServico → DataServico|Parcial|
|CodPeca → NomePeca|Parcial|
|CodPeca → PrecoUnitario|Parcial|
|CodServico + CodPeca → Quantidade|Total|

### Questão 4:

Não está em 2FN porque existem dependências parciais.


### Questão 5:

### COLOQUE A FOTO AQUI!