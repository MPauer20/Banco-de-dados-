
# Bancos de dados 
![Descrição da Imagem](https://previews.123rf.com/images/vitek5g/vitek5g1611/vitek5g161100021/65011867-black-database-icon-isolated-on-black-background-illustration.jpg)

## O que é ?
É uma coleção organizada de informações estruturadas, geralmente armazenadas eletronicamente em um sistema de computador. É uma ferramenta essencial para coletar, armazenar, gerenciar e recuperar dados de forma eficiente e confiável. 
Em termos mais simples, um banco de dados é como um arquivo digital onde informações são armazenadas de maneira organizada, permitindo que sejam acessadas e manipuladas rapidamente

## Tipos de banco de dados 
- Banco de dados não relacional
- Bancos de dados relacionais 

# O que é Banco de dados não relacional ?
 O banco de dados não relacional é um banco de dados que possibilita a flexibilidade na hora de armazenar os dados, já que não se limita a tabelas com linhas e colunas, como o banco de dados relacional. Esse tipo de banco de dados usa um modelo de armazenamento otimizado, que é adaptável para o requisito específico de cada dado, por exemplo: possibilita que os dados sejam armazenados como chave/valor simples; documento no formato JSON (JavaScript Object Notation) ou até mesmo em forma de gráfico, composto de bordas e vértices.

## Como funciona ?
NoSQL (Not Only SQL) é o termo utilizado para definir banco de dados não relacionais, frequentemente associados ao BigData. Esse método permite maior flexibilidade, escalabilidade e velocidade ao armazenar e acessar dados não estruturados, já que não tem necessidade de que as databases sejam parecidas entre si. Sendo assim diferente das relacionais.

## Exemplo
- Aplicações como redes sociais ou plataformas de e-commerce, onde os dados variam muito e não seguem um formato fixo

# O que é banco de dados relacional ?
Um banco de dados relacional é um tipo de banco de dados que armazena e fornece acesso a pontos de dados relacionados entre si. Bancos de dados relacionais são baseados no modelo relacional, uma maneira intuitiva e direta de representar dados em tabelas. Em um banco de dados relacional, cada linha na tabela é um registro com uma ID exclusiva chamada chave. As colunas da tabela contêm atributos dos dados e cada registro geralmente tem um valor para cada atributo, facilitando o estabelecimento das relações entre os pontos de dados.

## Como funciona ?
Um banco de dados relacional organiza informações em tabelas com linhas e colunas, onde cada linha representa um registro e cada coluna um atributo desse registro. Esses dados são estruturados e interconectados através de relações definidas por chaves primárias e estrangeiras, permitindo consultas complexas e análises eficientes

## Exemplo
- Magine um banco de dados para uma loja. Poderíamos ter uma tabela chamada "Clientes", com colunas como "ID_Cliente" (chave primária), "Nome", "Sobrenome", "Email", "Telefone". Cada linha nessa tabela representaria um cliente específico. 
Código

| ID_Cliente | Nome      | Sobrenome | Email             | Telefone  |
|------------|-----------|-----------|-------------------|-----------|
| 1          | João      | Silva     | joao.silva@email.com | (11) 9999-9999 |
| 2          | Maria     | Santos    | maria.santos@email.com | (11) 8888-8888 |

# o que é normalização ?
é um processo de organização e estruturação de dados em um banco de dados para reduzir a redundância e melhorar a integridade dos dados

## Objetivo
A normalização classifica as informações, fazendo com que uma base de dados seja fácil de administrar e manter, o que resulta em sua maior eficiência e desempenho. Além disso, diminui a redundância de dados e elimina anomalias, o que permite evitar erros e garantir a consistência e integridade de dados.1 de jun. de 2023

# Não normalização

 é o processo de introduzir redundância de dados propositalmente para melhorar o desempenho de consultas, especialmente em cenários onde a velocidade de leitura é crítica. Isso é feito sacrificando um pouco da integridade dos dados para otimizar a recuperação da informação. 

## Exemplo

| PedidoID | ClienteNome | ClienteTelefone | Produto1 | Produto2 | Produto3 | TotalPedido |
|----------|-------------|-----------------|----------|----------|----------|-------------|
| 1        | João Silva  | 99999-0000      | Camiseta | Boné     | -        | 80,00       |
| 2        | Ana Souza   | 98888-1111      | Vestido  | -        | -        | 120,00      |
| 3        | João Silva  | 99999-0000      | Camiseta | Tênis    | Boné     | 250,00      |



 # Normalização até a 3a Forma Normal (3FN) 
 ## Tabelas Aninhadas (Primeira Forma Normal - 1NF):
Uma tabela na 1NF não deve conter colunas com grupos de valores repetidos ou tabelas dentro de outras tabelas (tabelas aninhadas).
Cada coluna deve conter apenas um valor atômico (indivisível).
### Exemplo:
| Aluno_ID | Nome_Aluno | Curso         | Disciplina  | Nota |
|----------|------------|---------------|-------------|------|
| 1        | Ana        | Sistemas      | BD          | 8.0  |
| 1        | Ana        | Sistemas      | Redes       | 9.0  |
| 2        | João       | Sistemas      | BD          | 7.5  |
| 3        | Carla      | Administração | Finanças    | 6.0  |
| 3        | Carla      | Administração | Marketing   | 8.5  |


 ## Dependências Parciais (Segunda Forma Normal - 2NF):
Para estar na 2NF, uma tabela já deve estar na 1NF e não pode ter dependências parciais de chave primária.
Dependências parciais ocorrem quando um atributo não chave depende apenas de uma parte da chave primária composta, e não da chave primária como um todo.
### Exemplo:
 Aluno_ID | Nome_Aluno | Curso         |
### Tabela: Aluno

| Aluno_ID | Nome_Aluno | Curso         |
|----------|------------|---------------|
| 1        | Ana        | Sistemas      |
| 2        | João       | Sistemas      |
| 3        | Carla      | Administração |

### Tabela: Aluno_Disciplina

| Aluno_ID | Disciplina  | Nota |
|----------|-------------|------|
| 1        | BD          | 8.0  |
| 1        | Redes       | 9.0  |
| 2        | BD          | 7.5  |
| 3        | Finanças    | 6.0  |
| 3        | Marketing   | 8.5  |


 ## Dependências Transitivas (Terceira Forma Normal - 3NF):
Para estar na 3NF, uma tabela já deve estar na 2NF e não pode ter dependências transitivas.
Dependências transitivas ocorrem quando um atributo não chave depende de outro atributo não chave, que por sua vez depende da chave primária.
### Exemplo:
### 
| Curso_ID | Nome_Curso     |
|----------|----------------|
| 1        | Sistemas        |
| 2        | Administração   |

### Tabela: Aluno (atualizada)

| Aluno_ID | Nome_Aluno | Curso_ID |
|----------|------------|----------|
| 1        | Ana        | 1        |
| 2        | João       | 1        |
| 3        | Carla      | 2        |

### Tabela: Aluno_Disciplina

| Aluno_ID | Disciplina  | Nota |
|----------|-------------|------|
| 1        | BD          | 8.0  |
| 1        | Redes       | 9.0  |
| 2        | BD          | 7.5  |
| 3        | Finanças    | 6.0  |
| 3        | Marketing   | 8.5  |

---

##  Resumo das Formas Normais

| Forma Normal | Regras principais                                           | Benefícios principais                         |
|--------------|-------------------------------------------------------------|-----------------------------------------------|
| 1FN          | Eliminar grupos repetitivos e garantir dados atômicos       | Tabelas mais organizadas e fáceis de ler      |
| 2FN          | Eliminar dependências parciais (de parte da chave primária) | Redução de redundâncias                      |
| 3FN          | Eliminar dependências transitivas                           | Maior integridade e independência dos dados  |


