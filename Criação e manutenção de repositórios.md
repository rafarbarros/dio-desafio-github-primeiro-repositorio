# Criando e Clonando Repositórios

Alguns comandos para criarmos um `repositório` no Git.

1. Abrir o terminal Git, clicando com o direito do mouse sobre a pasta do projeto de origem, e selecionar a opção `Open Git Bash Here`, o terminal ja abrirá direto no diretório/pasta onde está seu projeto para commitar/clonar. Dessa forma, eliminamos todo o processo de ficar navegando entre as pastas;
   
3. `ls`, lista todos os arquivos presente nesse diretório, caso houver;
   
5. Podemos criar uma pasta a partir do terminal do Git, utilizando o comando `mkdir desafio-projeto`,onde `mkdir` é o comando que cria a pasta, e `desafio-projeto`,será o nome da pasta criada.

   Exemplo de local de trabalho no terminal.

   `/c/desktop/cursos/Git`
   
6. Para abrimos a pasta no terminal, utilizamos o comando `cd desafio-projeto/`, no caso do exemplo do local de trabalho citado acima, deverá ficar da seguinte forma `/c/desktop/cursos/Git/desafio-projeto/`;

7. Inicializamos um repositório nessa pasta com o comando `git init`;

- Uma pasta oculta é criada automaticamente pelo GitHub, essa pasta armazena e gerencia todos os códigos, sendo responsável pelo versionamento dos objetos que estão sendo manipulados. Essa pasta podo ser visualizada com o comando `ls -a`. ;

7. `git add *`, adiciona todos os arquivos que estão na pasta, e prepara eles para serem commitados.

- `git`, comando padrão Git;
- `add`, adiciona o arquivo para commit;
- ` * `, todos os arquivos da pasta serão preparados para commit;

>Caso não seja necessário adicionar todos os arquivos para comitar, deve-se apenas adicionar o nome do arquivo que se deseja.

Exemplo:

>`git add desafio-projeto`

8. `git commit -m " "` entre estas aspas duplas deve ser inserido uma mensagem curta, para que, quando acessarmos o repositório, saibamos doque se trata.
   
10. `git status`, monitora os status dos arquivos, se houve alguma alteração ou se algum arquivo foi adicionado ou removido da pasta de trabalho.
    
11. `mkdir novaPasta`, comando `mkdir` cria uma pasta.
    
12. `novaPasta`, é o nome dado a essa pasta.

    > Atenção ao dar o nome das pastas, se após o comando mkdir, o comando for este:
    
    `mkdir nova pasta`, será criado uma pasta com o nome de `nova` e outra pasta com o nome de `pasta`, devido ao espaçamento inserido entre as palavras ``nova`` e ``pasta``.

    >Para inserir uma única pasta, nesse exemplo o comando deverá ficar dessa forma:
    
    `mkdir novaPasta`, desse forma será criado apenas uma pasta com o nome de `novaPasta.
    
13. `mv nova /pasta/`, comando utilizado para mover o diretório `nova` para o diretório `pasta`
    
15. `echo > README.md` cria um arquivo na pasta de trabalho, onde `echo >` é o comando para criar o arquivo e `README.md` é o nome do arquivo criado.
    
16. `git push`, comando que possibilita que as alterações da sua máquina local sejam enviadas para uma máquina remota, no caso, o GitHub.

17. `git config --list` lista todas as configurações presentes na conta do Git / GitHub






