# Curso de Introdução ao SQL com Microsoft SQL Server 2017 + T-SQL com SQL Server 2012 Express

> Resumo dos conteúdos vistos do curso de SQL Server da Alura e do livro do autor Rodrigo Ribeiro Gonçalves.


## SQL 

* Linguagem de programação que é utilizada para realizar consultas de banco de dados;  

* Foi criada em 1974;

* É utilizada no mundo todo e sempre há demanda de mão de obra;

* Possibilita aos desenvolvedores recuperar informações no menor tempo possível.


## Banco de Dados

* São conjuntos de arquivos que se relacionam entre si e armazenam informações;

* Há vários tipos de SGBD's (Sistema de Gerenciamento de Banco de Dados) existentes, como o Microsoft SQL Management Studio, PostgreSQL, ORACLE, etc.;

    
    #### Más-práticas comuns no SQL

        * instruções mal-escritas;

        * colunas mal definidas e ocupando espaços desnecessários;

        * banco de dados no mesmo disco do sistema;

        * tabelas sem índices;

        * índices mal dimensionados;

        * instalação e configuração do SO;

        * dimensionamento errado do disco;

        * instalação errada/mal configurada do gerenciador do banco de dados;

## Por que implantar um banco de dados?

* aumento da masa de dados;

* crescimento do número de aplicações e usuários;

* aumento do número de servidores na mesma máquina.


## Definições

+ Tabela: representação lógica de um dado. Tipo de objeto que serve para alocar dados (campos e seus tipos);

    + Toda tabela, por default, é criada num esquema chamado **_dbo_**. Ela pode ser criada em outro esquema também;

+ Chave primária: campo que permite identificar uma tabela com mais de 2 milhões de linhas. Costuma ser do tipo de dado **_int_**;
    + Quando um campo é chave primária, ele também é índice;

+ Índice: estrutura na tabela que facilita a busca;

+ Chave estrageira: uma coluna é chamada de chave estrangeira quando faz referência à dados de uma coluna que é declarada **chave primária** em outra tabela. Ela pode conter dados nulos, porém todos os seus registros que estão preenchidos devem ter correspondência numa tabela.

+ references: recebe como argumento a tabela e o campo em que a receptiva chave primária foi definida. Dessa forma, todos os valores atribuídos aquela coluna devem ter correspondência em outra tabela.

_Sempre que criamos uma chave estrangeira, o SQL Server cria uma constraint para assegurar a integridade daquela chave estrangeira._

+ Consulta: visualização de uma determinada ou de um conjunto de tabelas.

    + Não é necessário o uso de ponto e vírgula;

+ View: estrutura lógica que é uma consulta (também lógica) a outras tabelas físicas;]

+ Procedures: processos que acontecem no BD;

    + Exemplo: manipulação de dados, cálculos, funções;

    + É necessário o uso de ponto e vírgula;

+ Triggers: comando único ou conjunto de comandos/funções que serão executados quando algo acontece numa tabela. Servem para manipular dados;

    + Precisa ser armazenada em alguma tabela ou view;

+ Página de dados: menor alocação de dados (possui o tamanho de 8 kbytes). É exclusiva de um objeto de alocação;

+ Extent: agrupamento lógico de página de dados. Tem exatamente 8 páginas de dados e possui o tamanho de 64 kbytes;

    + Extent misto: páginas de dados que são de objetos de alocações diferentes;

    + Extent uniforme: páginas de dados exclusivas de um único objeto de alocação;

            É regra do SQL Server começar com um Extent misto!!!

            O SQL Server acessa muito mais rápido a memória do que o disco.

+ Buffer: área de 8kbytes na memória onde o SQL Server armazena as páginas de dados lidas dos objetos de alocação que estão no disco (papel do Gereciador de Buffer).  

   + O dado permanece no Buffer, até que o Gerenciador de Buffer precise de mais áreas para carregar novas páginas de dados. As áreas do Buffer mais antigas e com dados modificados são gravadas em discos e liberadas para as novas páginas.

    + Quando o SQL Server necessita de um dado que é o mesmo que está no Buffer, ele faz uma leitura lógica desse dado. Se o dado não estiver no Buffer, o SQL Server faz uma leitura física do dado em disco para o Buffer Pool.

+ File Group: agrupamento lógico de arquivos de dados para distribuir melhor a alocação de dados entre os discos, agrupar dados de acordo com os contexros ou arquivamentos, e também permitir ao DBA (Administrador do Banco de Dados) uma melhor forma de administração.

+ Integridade Referencial: é uma propriedade referente aos valores de uma coluna de uma tabela de banco de dados. Todos os valores dessa coluna tem correspondência em outra coluna de outra tabela. Se essa condição for atendida, há integridade entre as tabelas.

## Normalização

### Primeira Forma Normal (1FN)

* É parte da definição formal da relação;

* Foi definida para não permitir atributos multivalorados, atributos compostos e suas combinações;

        "Uma relação só está na 1FN se seus atributos contêm apenas valores atômicos (simples, indivisíveis)."

### Segunda Forma Normal (2FN)

* Dependência parcial: ocorre quando uma coluna depende apenas de uma parte de uma chave primária composta;

* Uma relação para estar na 2FN não deve possuir atributos não-chave funcionalmente determinado por parte da chave primária;

        "Uma relação encontra-se na 2FN se e somente se estiver na 1FN e não contêm dependências parciais."

### Terceira Forma Normal (3FN)

* Dependência transitiva: ocorre quando uma coluna, além de depender da chave primária de uma tabela, depende de outra coluna ou conjunto de colunas da tabela;

* Uma relação, para não estar na 3FN deve ter um atributo não chave funcionalmente determinado por outro atributo não-chave;

        "Uma relação está na 3FN se e somente se não estiver na 2FN e nenhum atributo primo (isto é, que não seja membro de uma chave) for transitivamente dependente da chave primária."


## Tipos de dados

São os tipos de dados que armazenam o tamanho do que foi declarado ou definido para o tipo de de dado, sem aumentar ou diminuir o número de bytes de acordo com o dado inserido.


+ int: número exato, armazena sempre 4 bytes para representar números entre -2.147.483.648 e 2.147.483.648.
    
     + deve-se evitar o uso para valores pequenos (idade). Utilize para armazenar valores de cálculos, por exemplo.

+ smallint: número exato, que armazena sempre 2 bytes para representar números inteiros entre -32.768 e 32.768.

    + utilizado para identificar linhas em tabelas que há certeza que não ultrapassarão de 30.000 linhas;

    + utilizado para contagem ou para armazenar pequenas quantidades;

+ tinyint: número exato, armazena 1 byte para representar números inteiros positivos entre 0 e 255.

    utilizado para pequenos valores, tipificar colunas, contagens pequenas, número de dependentes;

+ bigint: número exato, armazena 8 bytes para representar números entre -9.223.372.036.854.755.808 até 9.223.372.036.854.755.807.

+ char(n): caractere, aceita 'n' bytes. Vai aceitar o total de bytes declarados, e ele terá o mesmo tamanhao para o armazenamento, independente da quantidade de caracteres associados.

    + Ex: Em um char(10), por exemplo, mesmo que você inclua a palavra "José" (4 bytes), o SQL Server irá gravar 10 bytes;

+ nchar(n): dado unicode, que aceita 'n' bytes, mas armazena 2 elevado a n bytes. Utiliza 2 bytes para representar um caractere.

    + É necessário colocar a letra "N" na frente do termo, seguido por aspas simples, para que seja identificado como unicode (N'termo aqui');

+ date: grava a data, sem hora, no formato DD/MM/AAAA. Armazena 3 bytes.

+ datetime: grava a data e a hora, no formato DD/MM/AAAA HH:MM:SS.SSS. Armazena 8 bytes, e não é padrão ANSI.

+ datetimeoffset: grava a data, hora, minuto, segundo e fuso horário.

+ smalldatetime: grava a data e a hora no formato DD/MM/AAAA HH:MM:SS.SSS. Armazena 4 bytes. Os segundos gravados são sempre zerados. Vai de 1970 até 2079.

+ time: grava a hora. Não armazena datas acumuladas.

+ money: representa um valor monetário e utiliza 8 bytes de armazenamento.

    + Pode ser utilizado para grandes quantias ou quando o armazenamento na linha for superior ao valor monetário de 241.718,3647.

+ smallmoney: representa o valor monetário. Utiliza 4 bytes de memória. Para representar acréscimos, descontos ou valores unitários, por exemplo.

+ decimal: dado com precisão decimal, no formato (0,0).

+ varchar(n): dado do tipo unicode que aceita no máximo n bytes e grava 2 bytes para cada caracter informado, e acrescenta mais 2 bytes para considerar o cálculo para gravar e recuperar os dados.

        Tipos de dados unicode somente devem ser utilizados se você realmente precisa gravar algum caracter com o código unicode acima de 255;

        Código de caracter de 0 até 255 são representados com 1 byte;

        Código de caracter de 256 até 65554 são representados com 2 bytes.

## Comandos

+ create database: cria o banco de dados;

+ drop database: apaga o banco de dados;


        Uso de [] - é utilizada quando um campo/entidade possui caracteres especiais.

+ cast: comando utilizado para convereter uma variável **int** em **varchar**.

        Declare
            @valor int
        set@valor = 1000
        print 'valor é' + cast(@valor as varchar)

Esse código também poderia ser escrito usando o comando **convert**, da seguinte forma:

        Declare
              @valor int
        set@valor = 1000
        print 'valor é' + convert(varchar, @valor)

Com o **convert** é necessário informar primeiro o tipo de dado e depois o valor a ser convertido.

A diferença entre os comandos é que o convert permite a existência de um terceiro argumento opcional, muito utilizado na conversão de datas.  

+ SP_HELP: Serve para visualizar a estrutura de uma tabela.

+ alter table: altera tabelas, seja adicionando ou removendo conteúdos.

        ALTER TABLE Clientes
        ALTER TABLE column DataNascimento DATETIME not null 
        

    + Adicionando um campo:


            ALTER TABLE Clientes
            ADD Codigo INT IDENTITY(1,1)
            Primary key   

            *caso o campo seja chave primária*

+ insert: insere novos registros numa tabela.

        INSERT INTO Clientes(
            Nome,
            Endereço,
            Numero,
            Cidade,
            Cep
        )
        VALUES
            ('Joana Maria da Silva', 'Rua das Cerejeiras, 133, Laranjais, 12456-890)

(Para inserir múltiplos valores com o comando, é só separar entre "()" as informações de cada nova inserção).

+ select: serve para retornar algum campo que você queira visualizar.

            SELECT * FROM Clientes

            (ou)

            SELECT 
                Codigo,
                Nome,
                GETDATE() AS [DataAtual]

+ where: serve para filtrar registros com base em alguns critérios. Você determina o que vai visualizar, comparando os campos com determinadas condições estabelecidas. Usa os operadores de comparação.

        SELECT
            Codigo,
            Nome,
            Endereco,
            Telefone, 
            Email,
            DataNascimento
        FROM
            Clientes
        WHERE
            Codigo > 1


### Operadores

+ and: envolve duas condições, pelo menos, que desejam ser visualizadas.

+ or: retorna valores que satisfazem uma ou outra condição.

+ between: exiibe uma faixa de comparação (um valor entre **x** ou **y**, por exemplo).

+ like: utilizado para buscar por uma determinada string dentro de um campo de caracteres. 

    + registros com o primeiro caractere do campo **nome** igual a "A", por exemplo).

+ like com colchetes []: serve para pesquisas mais complexas.  

    + Uma pesquisa pelos nomes Paula ou Paulo, por exemplo, ficaria da seguinte forma:

        
            SELECT * FROM Clientes
            WHERE LIKE 'Paul[ao]%'

+ top: limita a quantidade de registros que serão exibidos no **select**.

        SELECT
            TOP 2
            Codigo
        FROM
            Clientes

+ order by: dispõe os registros numa determinada ordem. Como argumento, espera apenas a indicação das colunas em que se deseja ordenar a seleção desejada. 

    + Por exemplo, para colocar os registros da tabela **Clientes** por ordem alfabética do campo nome:

            SELECT
                Codigo,
                Nome,
                Endereco,
                Telefone,
                Email,
                DataNascimento
            FROM
                Clientes
            ORDER BY
                Nome

+  update: permite atualizar registros em tabelas de um banco de dados.

        UPDATE
            Clientes
        SET 
            Endereco = 'Rua da Saudade', 'Florianópolis', 'SC', Telefone = '48625976'
        WHERE 
            Codigo = 1

+ isNull: é utilizado para tratar campos com valores nulos.

        ALTER TABLE Clientes
        ADD Cep VARCHAR(10)

        SELECT 
            Codigo,
            Nome,
            Endereco,
            Telefone,
            Email,
            DataNascimento,
            ISNULL (Cep, 'Sem Cep') as Cep
        FROM
            Clientes

+ coalesce: tem o mesmo propósito que a função **ISNULL**, porém a Coalesce faz parte do padrão ANSI, estando presente também em outros bancos de dados, diferente do **ISNULL** que é uma expressão do SQL Server.
Pode receber mais de dois parâmetros.

+ delete: serve para apagar um registro que foi inserido numa tabela.

            DELETE Clientes
            WHERE Codigo = 5

+ truncate table: serve para excluir todos os registros de uma tabela sem nenhuma discriminação.

        TRUNCATE TABLE Clientes

**_ATENÇÃO_**: o comando dá um **reset** na coluna **IDENTITY**, ou seja, a tabela tem todos os seus registros excluídos, e o primeiro registro a ser inserido tem o valor de **IDENTITY** igual a 1.

+ tabelas temporárias: são tabelas comuns, mas que existem apenas no escopo da seesão em que foram criadas, ou seja, não estão armazenadas fisicamente no banco de dados de maneira definitiva. Para criar uma, é só adicionar uma **#** antes de escreve o nome da tabela no momento da sua criação.

        CREATE TABLE #Clientes

Há outra forma de criar tabelas temporárias, com o uso de **SELECT** e **INTO**. A técnica cria uma **TABLE** temporária implicitamente já com os dados da tabela pré-existente.

        SELECT *
        INTO #Clientes
        FROM Clientes  

+ Tabelas temporárias se dividem em dois tipos:

    + Tabelas Locais: são criadas utilizando um **#**;

    + Tabelas Globais: utilizam dois **##** na frente do nome quando estão sendo criadas.


+ select into: permite a criação de tabelas físicas também. É só remover o **#**.

+ campo calculado: colunas virtuais que, por padrão, não estão armazenadas fisicamente no banco de dados. Estão dispostas apenas de maneira lógica. 
Uma coluna ou campo calculado tem várias aplicações, como listar uma data por extenso ou calcular operações aritméticas entre tabelas.

        ALTER TABLE Vendas
        ADD TotalVendas AS (Quantidade * ValorVenda)

+ joins: clásula da linguagem SQL que permite criar consultas combinando resultados de uma ou duas tabelas por meio de valores comuns entre tabelas. É possível visualizar os conjuntos existentes, intersecções, uniões e diferenças.

+ inner join: consulta os registros de duas tabelas e verifica todos os registros de cada uma, selecionando os que têm valores em comum, com base no critério estabelecido no **Join**.

        SELECT
            Nome, 
            DataVenda
        FROM
            Clientes c
        INNER JOIN Vendas V ON (C.Codigo = V.Clientes)

+ left join: permite obter não apenas os dados relacionados de duas tabelas, mas também os dados não relacionados na tabela à esquerda da clásula **Join**, marcado pelo sinal **=**.

        SELECT
            Nome,
            DataVenda
        FROM
            Clientes c
            LEFT JOIN Vendas V ON (C.Codigo = V.Clientes)

* right join: retorna os dados encontrados na tabela à direita do **Join** (=). Caso não existam dados associados entre às tabelas às esquerda e à direita de **Join**, serão retornados valores nulos.

        SELECT
            Descricao,
            DataVenda
        FROM
            Produtos p
        LEFT JOIN Vendas V ON (P.Codigo = V.Produto)

+ case: avalia uma lista de condições verificadas em um ou mais campos, e retorna apenas um de vários resultados possíveis.

        SELECT
            CASE
                WHEN <expressão lógica>
                    THEN <resultado da expressão 1>
                WHEN <expressão lógica 2>
                    THEN <resultado da expressão 2>
            ELSE
            <resultado fora das condições listadas>
            END
        FROM
            <tabela>

+ group by: permite agrupar registros baseados em um critério estabelecido no argumento da instrução posicionado logo após o comando.

        SELECT
            Nome,
            DataVenda
        FROM
            Clientes c
        INNER JOIN Vendas V ON (V.Cliente = C.Codigo)
        GROUP BY
            Nome,
            DataVenda

+ funções de agregação: fazem cálculos com um conjunto de valores determinados pela condição estabelecidas em clásulas **GROUP BY**.

    + count: conta os números de registros em uma condição **GROUP BY**.

            SELECT
                Nome,
                DataVenda
                COUNT (*) AS TotalVenda
            FROM
                Clientes c
            INNER JOIN Vendas V ON (V.Cliente = C.Codigo)
            GROUP BY
                Nome,
                DataVenda

    + sum: soma valores numéricos em um cojunto de valores estabelecidos pelo **GROUP BY**.

            SELECT
                Nome,
                DataVenda,
                SUM (ValorVenda AS TotalVenda)
            FROM
                Clientes c
            INNER JOIN Vendas V ON (V.Cliente = C.Codigo)
            GROUP BY
                Nome,
                DataVenda

    + avg: calcula a média de valores em um conjunto estabelecido pelo comando **GROUP BY**.

            SELECT 
                Descricao,
                SUM (quantidade * V.ValorVenda) AS TotalVenda,
                SUM (quantidade * V.ValorVenda),
                SUM (quantidade * P.ValorVenda) as Desconto - AVG ((quantidade * V.ValorVenda) - (quantidade * P.ValorVenda)) as Desconto
            FROM
                Clientes c
            INNER JOIN Vendas V ON (V.Cliente = C.Codigo)
            INNER JOIN Produtos P ON (V.Produto = P.Codigo)
            GROUP BY
                Descricao
            




