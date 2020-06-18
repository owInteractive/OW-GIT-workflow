![Logo OW Interactive](https://github.com/owInteractive/OW-GIT-workflow/raw/master/media/logo.jpg "OW Interactive")

# Guia para o Workflow que utilizamos no GIT

## Sobre a OW Interactive
Fazemos parte do universo digital, focada em criar e desenvolver experiências interativas, integrando planejamento, criatividade e tecnologia.

Conheça mais sobre nós em: [OW Interactive - Quem somos](http://www.owinteractive.com/quem-somos/).

## Requisitos Obrigatórios
- GIT [guia de instalação](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git);
- Gitflow [guia de instalação](https://danielkummer.github.io/git-flow-cheatsheet/index.pt_BR.html).

## Leituras Obrigatórias
- Fluxo de trabalho de Gitflow [ler](https://www.atlassian.com/br/git/tutorials/comparing-workflows/gitflow-workflow);
- Cheatsheet e exemplos visuais do Gitflow [ler](https://danielkummer.github.io/git-flow-cheatsheet/index.pt_BR.html);
- Utilizando o fluxo Gitflow [ler](https://medium.com/trainingcenter/utilizando-o-fluxo-git-flow-e63d5e0d5e04).

## Introdução
Ao ler os documentos acima, o flow deverá estar muito bem definida em sua cabeça, mas em todo caso, não se preocupe daremos uma explicação de como fazemos da OW.

Para startar o repositório em sua máquina em novos projetos, na pasta do projeto execute:

```git init```

Logo após, execute o comando abaixo para startar o flow.

```git flow init -f -d```

Com as opções **-f** e **-d** já serão criadas todas as branchs que irá precisar sem a necessidade de responder ao prompt interativo, caso deseje visualizar como as branchs e fluxo são criados basta retirar os dois paramêtros.

----------

Logo após esses processos, é criado o repositório no [Bitbucket](https://bitbucket.org/owinteractive) ou no [Github](https://github.com/owinteractive) e adicionado como **origin** do projeto. Após isso deverá ser feito um *pull* da **master** e da **develop** para o repositório remoto.

Por padrão utilizamos:

| Branch  |Ambiente  |
|-----------|------------|
|**develop**| Homologação|
|**master** |Produção  |

Sendo raros os casos que são criados releases, caso você esteja em algum projeto que utilize as releases para a produção, o funcionamento será um pouco diferente e nesse caso alguém da equipe deverá auxiliá-lo.

O fluxo poderá ter alguma variação conforme o projeto, mas se mantém nesse formato em 95% doas casos.

----------

O sistema de gerenciamento de itens e projetos utilizado é o [Jira](https://www.atlassian.com/br/software/jira), nesse caso suas tarefas, você deverá colocar na coluna **IN PROGRESS** e ao fazer isso você deve criar uma feature com base no identificador único da tarefa.

Por exemplo

![Exemplo Jira 01](https://github.com/owInteractive/OW-GIT-workflow/raw/master/media/jira-01.jpg "Exemplo Jira 01")

Na imagem acima, existe o identificador **OI-156** onde **OI** sinaliza que a tarefa é do projeto **OW Interactive** e **156** é o número do item.

Portando você deverá criar uma feature com o nome do identificador, conforme abaixo:

```git flow feature start OI-156```

> Caso você não tenha familiaridade com a linha de comando, você pode usar o [Source Tree](https://www.sourcetreeapp.com/), [Gitkraken](https://www.gitkraken.com/), [Git Tower](https://www.git-tower.com/mac), etc. Onde a maioria desses softwares já possuem uma integração com o Gitflow, portanto todos esses passos poderão ser realizados de forma visual.

Após realizar a tarefa conforme solicitado na descrição e testado em ambiente local, você deverá passar a tarefa para a coluna **IN REVIEW**

![Exemplo Jira 02](https://github.com/owInteractive/OW-GIT-workflow/raw/master/media/jira-02.jpg "Exemplo Jira 02")

Perceba que a tarefa foi passada de **IN PROGRESS** para **IN REVIEW**.

----------

Caso seja necessário antes de fechar a **feature** você pode solicitar para que outros desenvolvedores revisem o código que você criou ou alterou.

Para isso você deve criar uma **Pull Request** (PR) da sua branch para a branch **develop**, aqui vamos dar o exemplo utilizando o [Bitbucket](https://bitbucket.org/owinteractive) mas no [Github](https://github.com/owinteractive) é similar.

Você deve entrar na página do repositório no [Bitbucket](https://bitbucket.org/owinteractive) clicar em pull request no menu do lado direito.

![Bitbucket 01](https://github.com/owInteractive/OW-GIT-workflow/raw/master/media/bitbucket-01.jpg "Exemplo Bitbucket 01")

e na página que irá abrir clicar em **Criar Solicitação Pull** no canto direito superior.

Após isso será aberto uma nova página com os seguintes campos

![Bitbucket 02](https://github.com/owInteractive/OW-GIT-workflow/raw/master/media/bitbucket-02.jpg "Exemplo Bitbucket 02")

A maioria dos campos irá vir preenchido automaticamente, você deve então no select **Revisores** colocar quais serão os programadores que irão revisar a sua **PR**.

Feito isso vá também até o [Jira](https://www.atlassian.com/br/software/jira) com o Link gerado pelo bitbucket e os avise na tarefa também que foi criado uma PR para que revisem.

No processo de revisão caso seja apontado algum problema com o código ou lógica você deve voltar a tarefa para **IN PROGRESS** fazer a correção e seguir o fluxo proposto ou submeter outra **PR** caso seja necessário.

Caso tudo esteja certo e os revisores aprovarem a sua **PR** siga para a próxima etapa.

----------

A branch **feature** deverá ser fechada com o comando:

```git flow feature finish```

> Caso você não tenha familiaridade com a linha de comando, você pode usar o [Source Tree](https://www.sourcetreeapp.com/), [Gitkraken](https://www.gitkraken.com/), [Git Tower](https://www.git-tower.com/mac), etc. Onde a maioria desses softwares já possuem uma integração com o Gitflow, portanto todos esses passos poderão ser realizados de forma visual.

Após a finalização da branch, ela automaticamente irá ser enviada para a **develop**.

Realize o push para a **origin** no [Bitbucket](https://bitbucket.org/owinteractive) ou [Github](https://github.com/owinteractive), e logo após é só executar o comando para realizar o deploy em homologação.

> Mais detalhes de como realizar o deploy, você irá encontrar no [Confluence](https://www.atlassian.com/br/software/confluence) do projeto.

----------

Feito isso, avise o responsável pela tarefa, para que realize os testes finais em ambiente de homologação, após aprovação deverá seguir o fluxo.

> Caso o responsável de um retorno negativo todos os passos deverão ser refeitos.
>
> Caso o retorno seja positivo a tarefa será passada para a coluna **DONE**.

![Exemplo Jira 03](https://github.com/owInteractive/OW-GIT-workflow/raw/master/media/jira-03.jpg "Exemplo Jira 03")

e após a confirmação de que tudo está certo faça o merge da **develop** para a **master** e execute o deploy para produção.

----------

Pronto fluxo finalizado! É importante ter em mente que um ou outro projeto poderão ter alguma particularidade nesse processo, mas isso certamente será passado a você.

Qualquer sugestão para evolução desse guia ou processos não hesite em mandar no canal **#desenvolvimento** em nosso slack ou enviar uma PR (Pull Request) aqui mesmo no [Github](https://github.com/owinteractive).
