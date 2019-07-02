 * [ ] Criando títulos

Existem seis tamanhos de títulos. Quanto menor na proporção ele for, mais **#** são adicionadas;

        # Título 1

# Título 1

---

        ## Título 2

## Título 2

---

        ### Título 3

### Título 3

---

        #### Título 4

#### Título 4

---

        ##### Título 5

##### Título 5

---

        ###### Título 6  

###### Título 6  

---

Para separá-los, você pode usar  " **=** " ou " **-** ".   

---


* "Título 1
========" 

Título 1
========  


* "Título 2
--------" 

Título 2
--------  

---

 * [ ] Parágrafos

Podem ser quebrados de duas formas:

* dando dois espaços após o final da linha;
* apertando duas vezes o botão **enter** após o final do parágrafo.

---

 * [ ] Ênfase

- ### Negrito 1

 **Teste**
 
        **Teste** 

---

-  ### Negrito 2

__Teste__ 

        __Teste__ 

---

- ### Itálico 1

*Teste*

        *Teste*

---

- ### Itálico 2

 _Teste_

         _Teste_ 
 
---

- ### Negrito e Itálico 1

***Teste*** 

        ***Teste*** 

---

- ### Negrito e Itálico 2

**_Teste_**

        **_Teste_** 

---

- ### Negrito e Itálico 3

__*Teste*__ 

        __*Teste*__ 

---

- ### Riscado

~~Teste~~ 

        ~~Teste~~ 

---

- ### Citação

> Teste

        > Teste

---

- ### Citação com negrito e Itálico

> **Teste** _Teste_ 

        > **Teste** _Teste_ 

---
 * [ ] Linhas horizontais

- ### Exemplo 1

Podem ser feitas com asteriscos:
***

        ***

Ou com traços:

---

        ---

- ### Exemplo 2

Sejam juntos ou espaçados:

* * *

        * * *

- - - 

        - - - 

- ### Exemplo 3  

a única regra é colocar no mínimo três de cada símbolo.

*************** 

        ****************  

---------------  

        ----------------

 * [ ] Listas Não-Ordenadas 

- ### Exemplo 1

Um novo item é criado com " __*__ ".


* Item 1
* Item 2
* Item 3

--- 

- ### Exemplo 2

Utiliza-se o " **-** " para inserir um novo item.

- Item 1
- Item 2
- Item 3

---

- ### Exemplo 3

Utiliza-se o " **+** " para criar um novo item.  

+ Item 1
+ Item 2
+ Item 3

---

- ### Exemplo 4

Para criar um Subitem, crie um Item, dê dois **ESPAÇOS**, vá para a próxima linha, e aperte a tecla **TAB**.  


* Item 1  
        * Subitem 01
* Item 2  
        * Subitem 02
* Item 3  
        * Subitem 03

---

- ### Exemplo 5

Para deixar os itens espaçados, é só dar **ENTER** entre eles.

* Item 1

* Item 2

* Item 3

- - - 

 * [ ] Listas Ordenadas

- ### Exemplo 1

Uma lista é criada através de números em ordem crescente, seguidos de um ponto final.

1. Item 01
2. Item 02
3. Item 03

        1. Item 01
        2. Item 02
        3. Item 03

---

- ### Exemplo 2

Uma lista é criada atráves de números repetidos. O Markdown entende que a intenção é que esses números estivessem em ordem crescente.

1. Item 01
1. Item 02
1. Item 03

        1. Item 01
        1. Item 02
        1. Item 03

---

- ### Exemplo 3

Mesmo que os números sejam colocados em fora de ordem, eles seguirão a ordem crescente a partir do primeiro número. 

8. Item 01
3. Item 02
1. Item 03

        8. Item 01
        3. Item 02
        1. Item 03

---

- ### Exemplo 4

Quer escolher os números da sua lista? Não tem problema! Faça da seguinte forma:

1980\. Juliana  
1998\. Letícia  
2000\. Priscila

        1980\. Juliana  
        1998\. Letícia  
        2000\. Priscila

- - - 

 * [ ] Links

- ### Exemplo 1

O texto do link vai dentro de " **[]** ", e o link dentro de " **()** ".

[clique aqui](https://www.google.com)

        [clique aqui](https://www.google.com)

---

- ### Exemplo 2 

O texto do link vai dentro de " **[]** ", e o link dentro de " **()** ", porém um texto alternativo é inserido após o link através de **" "**. Esse texto será mostrado quando você parar seu mouse sobre o link.

[Clique aqui](https://www.google.com "blog")

        [Clique aqui](https://www.google.com "blog")

---

- ### Exemplo 3

Nesse exemplo, é criado uma espécie de variável, para qual o link será atribuído.

[Clique aqui][site-url]

[site-url]: (https://www.google.com/)

        [Clique aqui][site-url]

        [site-url]: (https://www.google.com/)

- - -

 * [ ] Imagens

É bem parecido com o formato dos links, mas sempre tem um " **!** " antes.

- ### Exemplo 1

O nome da imagem vai dentro de " **[]** ", e o link dentro de " **()** "

![Markdown](https://cdn.pixabay.com/photo/2019/06/19/13/16/scent-of-jasmine-4284856_960_720.jpg)

        ![Markdown](images/photo.png)
        
---

- ### Exemplo 2 

Aqui também é utilizado o esquema de variáveis.

 ![Markdown][image]

[image]: https://cdn.pixabay.com/photo/2019/06/28/03/07/camping-4303359_960_720.jpg

        ![Markdown][image]

        [image]: https://cdn.pixabay.com/photo/2019/06/28/03/07/camping-4303359_960_720.jpg

---

- ### Exemplo 3 - Imagem com link

Se você colocar o mouse em cima da imagem, verá seu link e poderá ser redirecionado para o mesmo.

[![Markdown](https://cdn.pixabay.com/photo/2018/12/08/11/03/escalators-3863163_960_720.jpg)](https://cdn.pixabay.com/photo/2018/12/08/11/03/escalators-3863163_960_720.jpg)


        [![Markdown](https://cdn.pixabay.com/photo/2018/12/08/11/03/escalators-3863163_960_720.jpg)]
        (https://cdn.pixabay.com/photo/2018/12/08/11/03/escalators-3863163_960_720.jpg)

---

- ### Exemplo 4 - Imagem com link (2)

Nesse exemplo, está sendo usado imagem, link e variável, tudo junto.

Variáveis: [image-thumbs], com o endereço da imagem, e [image-url], com o endereço do link.


[![Markdown][image-thumbs]][image-url]

[image-thumbs]: https://cdn.pixabay.com/photo/2019/06/27/03/42/beach-4301479_960_720.jpg

[image-url]: https://pixabay.com/pt/photos/praia-shell-de-mar-shell-f%C3%A9rias-4301479/


        [![Markdown][image-thumbs]][image-url]

        [image-thumbs]: https://cdn.pixabay.com/photo/2019/06/27/03/42/beach-4301479_960_720.jpg

        [image-url]: https://pixabay.com/pt/photos/praia-shell-de-mar-shell-f%C3%A9rias-4301479/

- - - 
 * [ ] Tabelas

- ### Exemplo 1

As tabelas são separadas por pipe " **|** ". Quando se deseja criar uma linha, utiliza-se " **-** ", para separar os dados.

| Nome |Idade |
|------|------|
| Joana |40 |

        | Nome |Idade |
        |------|------|
        | Joana |40 |

---

- ### Exemplo 2
 
Mesmo não existindo alinhamento, o Markdown identifica isso como uma tabela. 

| Nome | Idade| Profissão |
| ---- | ---- | --------- |
| Lua | 21 | Cientista de dados|
| Isabela | 32 | Dançarina |
| Raissa | 20 | Psicóloga comportamental|

        | Nome | Idade| Profissão |
        | ---- | ---- | --------- |
        | Lua | 21 | Cientista de dados|
        | Isabela | 32 | Dançarina |
        | Raissa | 20 | Psicóloga comportamental|
---

- ### Exemplo 3

Por padrão, o alinhamento das células é a esquerda. Para alinhar uma tabela:

+ A esquerda: **:---**  

+ A direita: **---:**  

+ Centralizada: **:---:**

| Nome | Idade| Profissão |
| :---- | :----: | ---------: |
| Igor | 36 | Professor |
| Carla | 29 | Advogada |
| Diogo | 15 | Estudante |

        | Nome | Idade| Profissão |
        | :---- | :----: | ---------: |
        | Igor | 36 | Professor |
        | Carla | 29 | Advogada |
        | Diogo | 15 | Estudante |

- - - 
 * [ ] Códigos

- ### Exemplo em linha

Informe os parâmetros `username` e `password` para a função `login ()`.

        Para destacar partes do texto/código, utilize a crase. Os parâmetros username e password foram destacados da seguinte forma:
        
        `username` e `password`

---

``const message  = `My name is $ {name}`;``

        Quando a declaração da variável não for código e for necessário transformar em código como na linha acima, faça da seguinte forma:

        ``const message  = `My name is $ {name}`;``
--- 

- ### Exemplo em bloco 1  

É só colocar um **TAB** antes de toda linha de código que se deseja inserir no bloco.  

        // login.js

        const username = 'gatinho99';
        const password = 'secret';

        login(username, password);

--- 

- ### Exemplo em bloco 2  

É inserido com três crases antes  (**```**) e três depois.

```
// login.js

const username = 'gatinho99';
const password = 'secret';

login(username, password);
```

        ```
        // login.js

        const username = 'gatinho99';
        const password = 'secret';

        login(username, password);
        ```
---

- ### Syntax hightlighting

Serve para mostrar ("acender") a sintaxe do código. Auxilia na identificação de valores da linguagem em questão.
Para usar o recurso, deve-se colocar o trecho de código entre crases, da seguinte forma:

        ```javascript

        //login.js

        const username = 'gatinho99';
        const password = 'secret';

        login (username, password);
        ```

O resultado será esse:

```javascript

//login.js

const username = 'gatinho99';
const password = 'secret';

login (username, password);
```

---

Outra forma de fazer é assim:

        ```js
        //login.js

        const username = 'gatinho99';
        const password = 'secret';

        login (username, password);
        ```

Resultado:

```js
//login.js

const username = 'gatinho99';
const password = 'secret';

login (username, password);
```
- - - 

 * [ ] Github

### Colocar 'caixinhas' nos ícones de uma lista:

* Item 01
* Item 02
* Item 03

        * Item 01
        * Item 02
        * Item 03

Colocando **[ ]** com um espaço no meio, ficará assim:

 * [ ] Item 01
 * [ ] Item 02
 * [ ] Item 03

         * [ ] Item 01
         * [ ] Item 02
         * [ ] Item 03

 --- 

### Relacionar pr com issue:

        Só colocar uma #;

---

## Emojis

:smile: 

:heart:

        :smile: 

        :heart:

Mais emojis [aqui](https://www.webfx.com/tools/emoji-cheat-sheet/) :D
