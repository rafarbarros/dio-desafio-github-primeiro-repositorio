## Oque é versionamento de Código

O versionamento de código é usado durante a construção de uma aplicação tecnológica, onde novas correções e implementações são criadas diariamente. Por isso é necessário trabalhar com o auxílio de ferramentas que ajudam no registro dessas modificações, indicando quem fez a mudança, quando e o que foi alterado.

## Oque é o Git

`O Git é um sistema de controle de versão DISTRIBUÍDO`, sendo um dos sistemas de versionamento mais utilizados atualmente, dado o fato de ser uma plataforma gratuita e open source, ou seja, de código aberto, onde o código-fonte é disponibilizado gratuitamente para consulta, examinação, modificação e redistribuição. Os produtos incluem permissão para usar o código-fonte, documentos de design ou conteúdo do produto.

# Oque é GitHub

Desenvolvido em 2008 por 4 desenvolvedores, sendo eles, Chris Wanstrath, J. Hyett, Tom Preston-Werner e Scott Chacon, e sendo vendida posteriormente, em 2018 pela Microsoft por US $ 7,5 Bilhões.

GitHub é uma plataforma de `hospedagem` de códigos para controle de versão, utilzando o git como ferramenta. Proporciona um ambiente colaborativo, ja que pode-se acessar códigos de diversos desenvolvedores, desde que, este código seja commitado (commit) de forma pública, é possível colaborar com o desenvolvedor sugerindo melhorias para o código, ou receber melhorias.

## Comandos básicos do Git e suas funcionalidades

- Ctrl + L : Limpa o terminal
- git config: Apresenta os comandos e funções para utilizar na plataforma.
- git clone : Clona um repositório Git existente para um novo diretório (pasta) local.
- git commit : Registra alterações que vão ser preparadas de um ambiente local para o repositório Git, permitindo uma breve descrição das mudanças.
- git pull : Busca e mescla alterações do repositório remoto para o repositório local.
- git push : "Empurra" as alterações do repositório local para o remoto.

# Configurando o Git

Com o terminal do GitBash aberto ( link na aba de Links Úteis), para o primeiro acesso é necessário fazer as configurações iniciais, cadastrando um nome de usuário e e-mail que foi utilizado para cadastro no GitHub. Para isso, utilizamos os comandos abaixo.

`git config --global user.name "entre estas aspas deve ser inserido um nome de usuário" + Enter`

`git config --global user.email seuemail@gmail.com (seu e-mail cadastrado no GitHub) + Enter`


Se a plataforma não retornar nenhum erro, as informações inseridas foram cadastradas corretamente, e caso necessite conferir essas informações, podemos utilizar os comandos abaixo:

`git config user.name `
- Retorna o nome de usuário cadastrado


`git config user.email`
- Retorna o email cadastrado

Essas informações cadastradas, serão utilizadas em commits realizados futuramente, caso as informações sejam alteradas (nome de usuário e email), os commits anteriores a essa mudança, essas informações não serão alteradas, somente os commits após a alteração.

# Definindo e consultando a Branch

`git config init.defaultBranch`

- Exibe a Branch configurada ativa

`git config --global init.defaultBranch main`

- Altera a Branch padrão para main

## Links Úteis
[&#128218; Documentação Git](https://git-scm.com/doc)

[&#9000; Site GitHub](https://github.com/)

[&#128187; Download Git / GitBash ( Win, Mac, Linux)](https://git-scm.com/downloads)

[&#128218; Sintaxe básica para formatação Markdown](https://www.markdownguide.org/basic-syntax/)
