<<<<<<< HEAD
# Ordem lógica de execução de uma query (Logical Query Processing Phase)

Acostumados frequentemente com linguagens de programação que possuem uma ordem de execução linear, quando nos deparamos com SQL a coisa muda de figura. Aparentemente, a ordem é bem clara quando vemos uma consulta, não? Pois é.  
Para entendermos melhor, vamos visualizar como a sintaxe do _**SELECT**_ é estruturada no SQL SERVER:


        SELECT DISTINCT TOP (<expressao_top>)
            <lista_select>
        FROM
            <tabela_esquerda>  <tipo_de_join> JOIN      
            
            <tabela_direita> ON <predicado_ON>
        WHERE
            <predicado_WHERE>
        GROUP BY
            <lista_group_by>
        HAVING
            <predicado_HAVING>
        ORDER BY
            <lista_ORDER_BY>

### Tá Lê, mas o que isso tem a ver?

Repare na forma como a consulta está estruturada. Ela possui os comandos *Select*, *From*, *Where*, *Group By*, *Having* e *Order By*. Acontece que, no SQL, a ordem de leitura desses comandos ocorre de maneira distinta das outras linguagens de programação frequentemente utilizadas. Cada clásula no SQL gera uma saída, podendo ser ela uma tabela virtual, ou um cursor (estrutura que permite o processamento das linhas retornadas por uma consulta **-SELECT-**, através de estruturas complexas de programação, como repetições ou comandos condicionais).

### Okay, mas como isso interfere na minha consulta?

A ordem de execução dos comandos muda (em relação ao que estamos acostumados). Entender essa prioridade nos ajuda a construir queries mais robustas e aplicáveis ao que desejamos retornar. A ordem seria a seguinte:

* **FROM:** Onde os _**Joins**_ são processados. Aqui é a primeira coisa que será levada em consideração quando uma consulta for executada.  
Os filtros filtros da clásula _**ON**_ (se houverem) também serão levados em consideração, e isso irá gerar uma tabela virtual;

* **WHERE:** É o responsável por filtrar e aplicar esses filtros na tabela gerada pelo _**FROM**_. Uma nova tabela virtual é gerada aqui;

* **GROUP BY:** É a clásula que pega a tabela virtual que foi gerada pelo comando _**WHERE**_ e a agrupa como foi solicitado. Gera outra tabela virtual;

* **HAVING:** É nessa clásula que filtros baseados em funções agregadas (_**AVG, SUM, MIN, MAX**_) são aplicados. Outra tabela virtual composta pelas colunas trazidas nessa filtro é gerada;

* **SELECT:** Aqui, todas as expressões contidas dentro do SELECT são avaliadas. Isso também inclui _**ALIAS**_, _**DISTINCT**_ e _**TOP**_. Uma tabela virtual é gerada;   

* **ORDER BY:** Promove a ordenação dos registros para que estes sejam apresentados. Sua saída é um _**cursor**_ que é retornado ao cliente quando a query é executada.

=======
# Ordem lógica de execução de uma query (Logical Query Processing Phase)

Acostumados frequentemente com linguagens de programação que possuem uma ordem de execução linear, quando nos deparamos com SQL a coisa muda de figura. Aparentemente, a ordem é bem clara quando vemos uma consulta, não? Pois é.  
Para entendermos melhor, vamos visualizar como a sintaxe do _**SELECT**_ é estruturada no SQL SERVER:


        SELECT DISTINCT TOP (<expressao_top>)
            <lista_select>
        FROM
            <tabela_esquerda>  <tipo_de_join> JOIN      
            
            <tabela_direita> ON <predicado_ON>
        WHERE
            <predicado_WHERE>
        GROUP BY
            <lista_group_by>
        HAVING
            <predicado_HAVING>
        ORDER BY
            <lista_ORDER_BY>

### <center>  Tá, mas o que isso tem a ver?

Repare na forma como a consulta está estruturada. Ela possui os comandos *Select*, *From*, *Where*, *Group By*, *Having* e *order by*. Acontece que, no SQL, a ordem de leitura desses comandos ocorre de maneira distinta das outras linguagens de programação frequentemente utilizadas. Cada clásula no SQL gera uma saída, podendo ser ela uma tabela virtual, ou um cursor (estrutura que permite o processamento das linhas retornadas por uma consulta **-SELECT-**, através de estruturas complexas de programação, como repetições ou comandos condicionais).

### <center>  Okay, mas como isso interfere na minha consulta?

A ordem de execução dos comandos muda (em relação ao que estamos acostumados). Entender essa prioridade nos ajuda a construir queries mais robustas e aplicáveis ao que desejamos retornar. Isso fica da seguinte forma:

* **FROM:** Onde os _**Joins**_ são processados. Aqui é a primeira coisa que será levada em consideração quando uma consulta for executada.  
Os filtros filtros da clásula _**ON**_ (se houverem) também serão levados em consideração, e isso irá gerar uma tabela virtual;

* **WHERE:** É o responsável por filtrar e aplicar esses filtros na tabela gerada pelo _**FROM**_. Uma nova tabela virtual é gerada aqui;

* **GROUP BY:** É a clásula que pega a tabela virtual que foi gerada pelo comando _**WHERE**_ e a agrupa como foi solicitado. Gera outra tabela virtual;

* **HAVING:** É nessa clásula que filtros baseados em funções agregadas (_**AVG, SUM, MIN, MAX**_) são aplicados. Outra tabela virtual composta pelas colunas trazidas nessa filtro é gerada;

* **SELECT:** Aqui, todas as expressões contidas dentro do SELECT são avaliadas. Isso também inclui _**ALIAS**_, _**DISTINCT**_ e _**TOP**_. Uma tabela virtual é gerada;   

* **ORDER BY:** Promove a ordenação dos registros para que estes sejam apresentados. Sua saída é um _**cursor**_ que é retornado ao cliente quando a query é executada.

>>>>>>> 6830cac6e8865030e2698f047a6feac7768f7021
