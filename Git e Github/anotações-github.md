# História do Git

A BitKeeper era uma empresa que armazenava todo o código do kernel do Linux em seu sistema, ou seja,todo o código do Linux era versionado dentro desse sistema. Houve uma quebra entre a BitKeeper e a Linux Foundation, que fez com que a BitKeeper retirasse o direito do Linux de ser isento (o que vai em contrapartida a proposta do SO). Linus Torvalds decidiu que não iria manter contrato com a empresa e resolveu criar seu próprio sistema de versionamento, incrementando melhorias que ele sentia falta no sistema da BitKeeper. Foram elas:  

- velocidade;
- simplicidade de uso;
- suporte robusto a desenvolvimento não linear;
- totalmente distribuído;
- eficiência para lidar com grandes projetos como o kernel do Linux;


        O Git é um sistema de controle de versionamento de código.
---

# Controle de versão

* É responsável por versionar os arquivos do seu projeto, facilitando para que você não precise fazer isso manualmente;  

* Os outros sistemas (SVM, Mercurial) trabalham com as diferenças dos arquivos, enquanto o Git trabalha com os estados deles (tira fotos _"snapshots"_ dos estados);  

* Todo estado sempre leva todos os arquivos daquele momento;

---

# Github

* É um local na web que serve para guardar projetos versionados pelo Git.

---

# Instalação

Acessar o [site](https://git-scm.com/download/win);


### Linux

* Não é necessário, pois já vem instalado;


### Windows

* Acesse o site, baixe e instale o programa. Você também pode seguir esse manual [aqui](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git);

### MacOs

* Se você instalar o XCode, o Git já vem junto. Também está disponível para ser baixado no site e você também pode consultar como instalá-lo pela linha de comando [aqui](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

---

# Configurações inciais do Git

O Git guarda as suas informações em três lugares:

* No git config do sistema como um todo;
* O git config do usuário;
* E o git config do projeto;   

---

* Configurando o usuário:

        git config --global user.name "Seu nome"

* Configurando o email:

        git config --global user.email "seuemail@email.com"

* Configurando o seu editor:

        git config --global core.editor "nome_do_seu_editor"

+ Para descobrir os valores atrabuídos a cada uma dessas configurações, é só digitar "git config" seguido do parâmetro que você deseja saber. Exemplo:

        git config user.name

* E para saber tudo, digite:

        git config --list

---

# Criando um repositório

### Criando uma pasta

* Linux

        mkdir "nome da pasta"

* Windows

        md "nome da pasta"

* MacOS

        mkdir "nome da pasta"


### Entrando dentro da pasta

* Todos

        cd "nome da pasta"

* Para voltar a uma pasta acima da que vocẽ está, basta digitar:

        cd ..

### Para iniciar um repositório

        git init 

### Listar os arquivos da pasta

* Linux e Mac

        ls

* Windows 

        dir

---

### Usando o editor no terminal

O **Vim** é um editor de texto muito utilizado para quem gosta de trabalhar pelo terminal. Ele está disponível para Windows, Mac e Linux e caso o seu computador não tenha ele instalado, você pode encontrá-lo [aqui](https://www.vim.org/download.php).


* Para editar um arquivo:  


        vi "nome do arquivo"

    ou  

        vim "nome do arquivo"

* Para começar a inserir texto, aperte a letra

        i
    que significa inserção;


* Digite o texto desejado;

* Pressione a tecla

        esc

    serve para sair do modo de inserção;


* Depois, digite:

        :

    que indica que vai iniciar algum comando;


        w

    que significa que você deseja escrever/salvar;

        q

    que significa sair.


* E agora aperte

        enter

    você sai do modo de edição e seu arquivo está salvo;

    



