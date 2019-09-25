# Curso SQL Server 2017 Developer Expert SQL e T-SQL

Esse curso pode ser encontrado [aqui](https://www.udemy.com/course/sqlserver-2017-developer-expert/).

Segundo a definição de Korth, banco de dados "é uma coleção de dados inter-relacionados, representando informações sobre um domínio específico". Isso significa que, sempre que for possível agrupar informações que se relacionam e falam de um mesmo tema, pode-se dizer que há um banco de dados.

Eles são repositórios que permitem ao computdor manusear grades volumes de dados com quais empresas e pessoas precisam lidar no dia a dia.

Exemplos comuns de banco de dados: agenda, lista telefônica. 
Hoje em dia, graças a tecnologia, bancos de dados são armazenados de forma digital.

Existe uma necessidade absurda de armazenar, organizar e recuperar informações. Um BD é utilizado para fazer isso.

| Acrescentar | Localizar | Alterar | Apagar |
| ----------- | --------- | ------- | ------ |
| Insert | Select | Update| Delete |

As informações de um banco são armazenadas em tabelas. Tabelas são uma maneira de organizar informações em listas e colunas;

Cada linha pode ser chamada de *registro* e *tupla* também.

Um *campo* é um espaço dentro de uma linha da tabela que guarda algum tipo de dado.

## Conceitos de um banco de dados relacional

* Permite o controle de redundância de dados (evita a criação de dados repetidos);

* Garante a integridade dos dados;

* Garante a privacidade, através de mecanismos de segurança dos dados;

* Possibilita a otimização do espaço de armazenamento;

* Controle automático de relacionamento entre tabelas de dados;

* Possibilita criar bancos com performance de acesso a informação;

* Dentro de um banco de dados, cada tabela deve ter um nome único;

* Cada coluna tem um nome único (um nome de coluna só pode ser repetido em outra tabela);

* Colunas possuem atributos e todos devem ser do mesmo domínio;

* Linhas armazenam informações de um registro (ou tupla) da tabela;

 * Cada célula pode conter no máximo um item de dado;

 * A ordem das linhas e colunas é irrelevante (nomes e chaves primárias costumam ser os primeiros campos criados);

 * Nunca existem duas linhas iguais;

 * Chave primária é um registro sequencial que garante que nunca hajam duas linhas idênticas;

* ID's servem para fazer relacionamentos entre tabelas (é a notação comumente utilizada para as chaves primárias);


## MER: Modelo entidade-relacionamento

* É um modelo conceitual utilizado na Engenharia de Software, que serve para fazer a descrição dos objetos (entidades) envolvidos em um modelo de negócios, com suas características (atributos), e seus relacionamentos (maneira que elas se relacionam entre si);

* Em geral, apresenta de forma abstrata como será estruturado o banco de dados da aplicação. Esse banco também pode conter outras entidades, chaves e tabelas intermediárias, que só fazem sentido no contexto de bases de dados relacionais;

### Entidades

* Os objetos ou partes envolvidas num domínio, também chamados de entidades, podem ser classificados como _físicos_ ou _lógicos_.

    + **Entidade física**: aquelas realmente tangíveis, existentes e visíveis no mundo real, como um cliente (uma pessoa, uma empresa) ou um produto (um carro, um computador, uma roupa);
    + **Entidades lógicas**: existem normalmente em decorrência da interação entre entidades físicas ou com elas. Isso faz sentido dentro de um determinado domínio de negócios, mas no mundo real não são objetos físicos (ou seja, não ocupam lugar no espaço). Exemplos: venda, classificação por modelo, espécie, função/cargo;

* Entidades são nomeadas com substantivos que representem de forma clara sua função dentro do domínio;

### Tipos de entidade

* **Forte**: são aquelas que possui existência independente de outras entidades. Exemplo: num sistema de vendas, a entidade *produto* independe de qualquer outra para existir;

* **Fraca**: são aquelas que dependem de outra entidade para existirem, pois individualmente elas não fazem sentido. Exemplo: a entidade venda depende da entidade produto, pois uma venda é composta por itens;

* **Associativa**: surge quando há a necessidade de associar uma entidade a um relacionamento que já existe;

### Cardinalidade

* **1 para 1 (1-1)**: Cada uma das duas entidades envolvidas referenciam, *obrigatoriamente*, apenas uma unidade da outra.  
Exemplo: em um banco de dados de currículos, cada usuário cadastrado pode possuir apenas um currículo na base, ao mesmo tempo em que cada currículo só pertence a um único usuário cadastrado.

* **1 para muitos (1-N)**: Uma das entidades envolvidas pode referenciar várias unidades da outra, porém, do outro lado cada uma das várias unidades referenciadas só pode estar ligada a uma unidade da outra entidade.   
Exemplo: num sistema de plano de saúde, um usuário pode ter vários dependentes, mas cada dependente só pode estar ligado a um usuário principal. Há apenas duas entidades envolvidas: *usuário* e *dependente*. O que muda é a quantidade de unidades envolvidas em cada lado;

        Uma pessoa pode ter muitos carros.

 * **Muitos para muitos (N-N)**: Aqui cada entidade, independente do lado, pode referenciar múltiplas unidades da outra.  
 Exemplo: em um sistema de biblioteca, um título pode ser escrito por vários autores, ao mesmo tempo em que um autor pode escrever vários títulos. Assim, um objeto do tipo *autor* pode referenciar múltiplos objetos do tipo *título*, e vice versa.

 ## Propriedades das transações
 
### ACID

* **Atomicidade**: uma transação é uma unidade atômica de processamento. Ou ela é executada em sua totalidade, ou então nada é executado;

* **Consistência**: a execução de uma transação precisa manter a consistência de um banco de dados;

* **Isolamento**: uma transação não deve disponibilizar para outras transações as modificações feitas em um banco de dados até que essa seja encerrada com sucesso;

* **Durabilidade**: uma vez executada com sucesso, as alterações devem ser gravadas no banco de dados;

### CRUD

* **Create**: cria os objetos do banco de dados;
* **Read**: lê os objetos do banco de dados (*select*);
* **Update**: atualiza os objetos do banco de dados;
* **Delete**: apaga os objetos do banco de dados;

## SQL (Structured Query Language)

A primeira versão da linguagem, antigamente chamada SEQUEL, surgiu em 1972 nos laboratórios da IBM, na Califórnia. Entre 1976 e 1977 foi melhorada e ampliada, sendo chamada de SQL.

Em 1982, a ANSI (American National Standard Institute) SQL se tornou a linguagem padrão para manipulação de dados em ambiente relacional.

* **Usos**: 

    * Linguagem interativa de consulta (query AdHoc): atravpes de comandos SQL, os usuários podem montar consultas poderosas sem precisar criar um programa;

    * Linguagem de programação para acesso às bases de dados: Comandos SQL que são embutidos em programas de aplicação (desenvolvidos em Python, .Net, Java, etc.) podem acessar as informações armazenadas em uma base de dados relacional;


### Microsoft SQL Server

Sistema gerenciador de banco de dados relacional desenvolvido pela Microsoft (popularmente conhecido como SGBD);

* Serviços

| Serviço do SQL Server | Principal Função |
| --------------------- | -----------------|
| Database Engine       | Armazenamento de dados OLTP |
| Reporting Services    | Relatório de dados |
| Analysis Services     | Análise de dados OLAP |
| Integration Services  | Fluxos de dados |
| Data Quality Services | Limpeza de dados |
| Master Data Services  | Repositório único de dados |
| Replicação            | Replicação de dados entre servidores| 


## Tipos de dados

O tipo de dado se dá pelo formato em que a informação será armazenada no banco de dados. 

* Cadeias de caracteres:

    + **char(n)**: Sequência de caracteres de tamanho fixo. Máximo 8000 caracteres;

    + **varchar(n)**: Sequência de caracteres de tamanho variável. Máximo 8000 caracteres;

    + **varchar(max)**: Sequência de caracteres de tamanho variável. Máximo 1.073.741.824 caracteres;

    + **text**: Sequência de caracteres de tamanho variável. Máximo 2gb de dados de texto;

* Cadeias de caracteres unicode:

    + **nchar(n)**: Sequência de caracteres de tamanho fixo. Máximo 4000 caracteres;

    + **nvarchar(n)**: Sequência de caracteres de tamanho variável. Máximo 4000 caracteres;

    + **nvarchar(max)**: Sequência de caracteres de tamanho variável. Máximo 536.870.912 caracteres;

    + **ntext()**: Sequência de caracteres de tamanho variável. Máximo de 2gb de dados de texto;

* Cadeias de caracteres binárias:
    + **binary**: Dados binários de comprimento fixo com um comprimento de n bytes, em que n é um valor de 1 a 8000. O tamanho de armazenamento é em bytes;

    + **image**: Dados binários do comprimento variável de 0 a 2^31-1 (2.147.483.647) bytes;

    + **varbinary**: Dados binários de comprimento vari´vel, n pode ser um valor de 1 a 8000. Max indica que o tamanho de armazenamento máximo é 2^31-1 bytes.

* Data e hora:

* Números exatos:
* Números aproximados: 

==========================================

## Constraints 

São utilizadas para especificar regras de armazenamentos de dados nas tabelas e garantir integridade.

Tipos:

* **Not null**: garante que uma coluna não receberá valor NULL;

* **Unique**: Garante que os valores em uma coluna sejam diferentes;

* **Primary key**: Chave única, linha exclusiva com, combinação com

* **Foreign key**: Referencia o vlaor de um campo em determinada linha a outra tabela;

* **Default**: Define um valor padrão para uma coluna quando nenhum valor é especificado;

* **Index**: Usado para criar e recuperar dados do banco de dados com melhor performance;

* **Check**: Valida o valor 


=========================================

## Definições da linguagem SQL (DML, DDL, DCL, TCL)

* **DML** (Data Manipulation Language): manipulação da linguagem.  
*Comandos*: 

    + SELECT: recupera dados do banco de dados;

    + INSERT: insere dados em uma tabela;
    + CREATE: para criar objetos no banco de dados, o próprio banco de dados, tabelas, indexes, views, functions e triggers;

    + UPDATE: atualiza os dados existentes em uma tabela;
    
    + DELETE: exclui registros da tabela.

* **DDL** (Data Definition Language): criação dos objetos da linguagem. 
*Comandos*: 


    + ALTER: altera a estrutura da base de dados, o próprio banco de dados, tabelas, indexes, procedures, views, functions e triggers;

    + DROP: apaga objeto do banco de dados,

    + TRUNCATE: remove todos os registros de uma tabela, incluindo todos os espaços alocados para os registros que são removidos.

* **DCL** (Data Control Language): controle de acesso aos objetos.  

*Comandos*: 
    + GRANT:, REVOKE, GRANY.

* **TCL** (Transaction Control Language): controle de transação da linguagem.  
*Comandos*: BEGIN TRANSACTION, COMMIT, SAVE, SAVE TRANSACTION, ROLLBACK.