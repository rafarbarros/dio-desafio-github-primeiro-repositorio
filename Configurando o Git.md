# Configurando o Git

Com o terminal do GitBash aberto ( link na aba de Links Úteis), para o primeiro acesso é necessário fazer as configurações iniciais, cadastrando um nome de usuário e e-mail que foi utilizado para cadastro no GitHub. Para isso, utilizamos os comandos abaixo.

`git config --global user.name "entre estas aspas deve ser inserido um nome de usuário" + Enter`

`git config --global user.email seuemail@gmail.com (seu e-mail cadastrado no GitHub) + Enter`


Se a plataforma não retornar nenhum erro, as informações inseridas foram cadastradas corretamente, e caso necessite conferir essas informações, podemos utilizar os comandos abaixo:

`git config user.name `
- Retorna o nome de usuário cadastrado


`git config user.email`
- Retorna o email cadastrado

Essas informações cadastradas, serão utilizadas em commits realizados futuramente, caso as informações sejam alteradas (nome de usuário e email), os commits anteriores a essa mudança não serão alterados, somente os commits após a alteração.

# Definindo e consultando a Branch

`git config init.defaultBranch`

- Exibe a Branch configurada ativa

`git config --global init.defaultBranch main`

- Altera a Branch padrão para `main`

# Autenticação via Token de repositórios privados

Anteriormente era possível realizar autenticações de repositórios privados entre as plataformas Git/GitHub, utilizando o email e senha cadastrada, mas desde 13 de agosto de 2021, essa forma de autenticação foi removida, sendo necessário a criação de chaves token para autenticar uma alteração.

A autenticação via token, se dá quando desejamos realizar uma alteração em algum repositório privado, esse tipo de repositório é criado quando o intuito é não disponibilizar seus projetos na plataforma de forma que  outros usuários não vejam esse repositório no seu perfil, ou quando o projeto deve ficar restrito somente a equipe envolvida no desenvolvimento.

- Para criação de uma chave token, podemos seguir os processos abaixo:

1. Com sua conta no GitHub devidamente logada, abrir a aba no canto superior onde consta sua foto de perfil e abrir a opção `settings`;

2. Selecionar a opção `Developer Settings`, localizada na coluna de opções a esquerda (a última opção);
3. Selecionar a opção `Personal access tokens`, localizada na coluna a esquerda;
4. Selecionar a opção `Tokens (classic)`;
5. Selecionar a opção `Generate new token`;
6. Selecionar a opção `Generate new token(classic)`, nessa etapa será necessário uma autenticação da sua conta GitHub.
7. Na aba `note`, podemos inserir a descrição, finalidade do cadastro da chave token.
8. Na aba `Expiration`, é possível inserir o tempo que essa chave ficará ativa, após esse tempo, a chave expira, sendo necessário a geração de uma nova chave.
9. Na aba `Select scopes`, é possível selecionar quais as permissões o usuário deseja fornecer a chave cadastrada
- Exemplo: Selecionando a opção `repo`, será concedido controle total dos repositórios privados.
10. Selecionar a ooção `Generate token`, localizada no final das opções de scopes;

Com a chave token criada, é possivel copiá-la e utilizar essa chave para autenticação de commits realizados no Git.

> *__Por motivos de segurança, após sair da tela onde se encontra a chave criada, a mesma não poderá mais ser visualizada, recomenda-se a utilização imediata__*.

# Utilizando chave Token para autenticação

Com o terminal Git aberto no caminho aonde se deseja clonar o repositório, segue os comandos.

1. `git clone` + URL do repositório que se deseja clonar + Enter. Esta URL está disponivel na página principal do repositório, clicando em `<> Code`, seleciona-se a aba `HTTPS` e copia-se a URL logo abaixo;
2. Se for o caso de abrir uma caixa de diálogo `Git for Windows`, apenas cancele e volte ao terminal;
3. Informe o nome de usuário cadastrado no GitHub;
4. Nesse passo, será solicitado uma senha, aqui deve ser inserido a chave token gerada. No terminal, após inserida a chave, por motivos de segurança ela não é exibida. Após inserir a chave confirme com a tecla enter;
5. Se não houver nenhum erro, a clonagem deve prosseguir e ser validada;

Caso o projeto que esteja trabalhando, exija muitos procedimentos de autenticação, há a opção de salvar a chave token na própria maquina do usuário, utilizando o terminal Git, não sendo necessário criar novas chaves a todo momento.

`git config --global credential.helper cache` salva a chave temporariamente;

`git config --global credential.helper store` salva a chave permanentemente;

`git config --global credential.helper` Informa o valor definido na configuração de salvamento da chave `cache` ou `store`

Dessa forma, sempre que realizar uma operação que precisar de autenticação, esta será feita de forma automática, não é solicitado as credenciais como nome de usuário e senha.

# Autenticando via chave SSH

Uma outra possibilidade de autenticação de solicitações no Git é utilizando uma chave do tipo SSH ( Secure Shell). 
Este tipo de chave, `trabalha com um par de chaves (pública e privada)`, utiliza um protocolo de rede que possibilita que seu computador local e o servidor remoto, no caso o GitHub, se conectem de forma segura e criptografada por meio da internet.

>Antes de criar esse tipo de chave, podemos verificar se há alguma chave configurada. 

1. Com sua conta no GitHub devidamente logada, abrir a aba no canto superior onde consta sua foto de perfil e abrir a opção `settings`;
2. Na coluna a esquerda na aba `Access`, selecionar a opção `SSH and GPG keys`;
3. No título SSH keys, selecione a opção `generating SSH keys` destacado em azul;
4. Na nova janela que se abre, selecionar a opção `Verificar se há chaves SSH`;
5. Selecione o sistema operacional que você está utilizando ( Windows, Mac, Linux), nesse exemplo será utilizado Windows;
6. Nessa tela, é informado todos os procedimentos necessários para verificação, definidos abaixo;
7. Abra a plataforma Git Bash;
8. Insira o comando `ls -al ~/.ssh` + enter, para verificar se há chaves SSH configuradas.
9. Se o terminal retornar a mensagem `No such file or directory`, indica que não há chaves configuradas;

>Configurando uma chave SSH.

1. Abra o Git Bash;
2. Insira o comando `ssh-keygen -t ed25519 -C "entre essas aspas deve ser informado seu email do GitHub"` + enter;
3. Tecle enter para selecionar o destino padrão para salvar a chave gerada;
4. Digite uma frase/palavra para ser utilizado como senha + enter;
5. Se não retornar nenhum erro, a chave pública e privada foi criada;

Após esses procedimentos, no guia de geração de chave SSH do GitHub, pede-se a adição dessa chave no `ssh-agente`, que será responsável pelo gerenciamento e armazenamento da chave gerada de forma segura.

1. Na plataforma do Git Bash insira o comando `eval "$(ssh-agent -s)"` , inicializado o ssh-agent;
2. Agora é necessário adicionar nossa chave privada ao ssh-agent, utilizando o comando `ssh-add ~/.ssh/id_ed25519`;
3. Insira a frase/palavra cadastrada anteriormente como senha na configuração da chave SSH;
4. Se não retornar nenhum erro, a chave privada foi adicionada ao ssh-agent;

O próximo passo é adicionar a chave SSH pública a conta o GitHub.

1. 1. Com sua conta no GitHub devidamente logada, abrir a aba no canto superior onde consta sua foto de perfil e abrir a opção `settings`;
2. Na coluna a esquerda na aba `Access`, selecionar a opção `SSH and GPG keys`;
3. Selecionar a opção `New SSH key`, um botão destacado em verde ao lado direito da tela;
4. Insira um título para a chave que será adicionada a sua conta do GitHub;
5. Selecione na aba `Key type` a opção `Authentication key`
6. Na aba `key` é necessário inserir a chave pública configurada, para isso abra o terminal Git e insira o comando `cd ~/.ssh`;
7. `ls` lista as chaves configuradas, utilizaremos a chave de extensão `.pub`;
8. `cat id_ed25519.pub`, será exibido o conteúdo da chave publica, selecionamos todo o conteúdo e copiamos(cuidado para copiar a chave corretamente, a chave deve ficar inserida toda em apenas uma linha);
9. Retornando a aba `key` la no GitHub, colamos essa chave e selecionamos a opção `Add SSH key`, botão verde logo abaixo;
10. Insira o código de autenticação, caso esteja configurado a verificação de 2 fatores, ou algum aplicativo de autenticação configurado, ou podemos utilizar a opção logo abaixo destacada em azul `Use your password` e digitar sua senha do GitHub.
11. Se não retornar nenhum erro, a chave foi adicionada, podendo ser conferida nas opções de `SSH and GPG keys`, mostrado anteriormente;

Para o primeiro uso, caso a plataforma Git solicitar uma confirmação por motivos de segurança, digitamos `yes`para continuar, e em seguida inserimos a frase/palavra configurada anteriormente como senha.

## Links Úteis
[&#128218; Documentação Git](https://git-scm.com/doc)

[&#9000; Site GitHub](https://github.com/)

[&#128187; Download Git / GitBash ( Win, Mac, Linux)](https://git-scm.com/downloads)

[&#128218; Sintaxe básica para formatação Markdown](https://www.markdownguide.org/basic-syntax/)
