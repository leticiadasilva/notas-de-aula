# Curso de Introdução ao SQL com Microsoft SQL Server 2017 + T-SQL com SQL Server 2012 Express

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

+ Chave primária: campo que permite identificar uma tabela com mais de 2 milhões de linhas. Costuma ser do tipo de dado **_int_**;

+ Chave estrageira: serve para estabelecer a ligação entre uma tabela e outra (relacionamento);

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

        

    


