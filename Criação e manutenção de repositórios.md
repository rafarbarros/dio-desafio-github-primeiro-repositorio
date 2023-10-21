# Criando e Clonando Repositórios

Para iniciar e criarmos um `commit` no Git, segue os passos.

1. Abrir o terminal Git, clicando com o direito do mouse sobre a pasta do projeto de origem, e selecionar a opção `Open Git Bash Here`, o terminal ja abrirá direto no diretório/pasta onde está seu projeto para commitar/clonar. Dessa forma, eliminamos todo o processo de ficar navegando entre as pastas;
2. `ls`, lista todos os arquivos presente nesse diretório, caso houver;
3. Podemos criar uma pasta a partir do terminal do Git, utilizando o comando `mkdir desafio-projeto`,onde `mkdir` é o comando que cria a pasta, e `desafio-projeto`,será o nome da pasta criada.

   Exemplo de local de trabalho no terminal.

   `/c/desktop/cursos/Git`
   
4. Para abrimos a pasta no terminal, utilizamos o comando `cd desafio-projeto/`, no caso do exemplo do local de trabalho citado acima, deverá ficar da seguinte forma `/c/desktop/cursos/Git/desafio-projeto/`;

5. Inicializamos um repositório nessa pasta com o comando `git init`;

- Uma pasta oculta é criada automaticamente pelo GitHub, essa pasta armazena e gerencia todos os códigos, sendo responsável pelo versionamento dos objetos que estão sendo manipulados. Essa pasta podo ser visualizada com o comando `ls -a`. ;

7. `git add *`, adiciona todos os arquivos que estão na pasta, e prepara eles para serem commitados.

- `git`, comando padrão Git;
- `add`, adiciona o arquivo para commit;
- ` * `, indica que deve ser selecionado todos os arquivos da pasta para commit;

8. `git commit -m " "` entre estas aspas duplas deve ser inserido uma mensagem curta, para que, quando acessarmos o repositório, saibamos doque se trata.






