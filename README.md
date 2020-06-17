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
Caso você tenha lido os artigos acima, acredito que a ideia do flow já irá estar muito mais definida em sua cabeça, mas caso haja alguma dúvida vamos dar uma explicação de como fazemos.

Caso você for começar um novo projeto utilize esse comando para startar o reposítorio em sua máquina, na pasta do projeto execute.

```git init```

Com o projeto iniciado iremos startar o flow, com o seguinte comando. Com as opções **-f** e **-d** será já criadas todas a branchs que precisamos sem a necessidade de responder o prompt interativo, caso queira visualizar como as branchs e fluxo é criado fique a vontade para retirar os dois paramêtros.

```git flow init -f -d```

Após isso geralmente criamos o reposítorio no [Bitbucket](https://bitbucket.org/owinteractive) ou no [Github](https://github.com/owinteractive) e adicionamos como **origin** do nosso projeto. Após isso fazemos um pull da master e da develop para o reposítorio remoto.

Por padrão utilizamos como homologação a branch **develop** e para produção a **master** são raros os casos que criamos releases, caso você esteja em um projeto que utilize as releases para a produção, o funcionamento será um pouco diferente do que é passado, aqui nesse caso, alguém irá auxiliá lo.

O Fluxo no dia a dia, é basicamente esse tendo uma ou outra variação conforme o projeto, mas o mesmo se mantém em 95% dos casos.

Caso seja lançada uma tarefa pra você no [Jira](https://www.atlassian.com/br/software/jira) você deve colocar a mesma na coluna **In Progress** ao fazer isso você deve criar uma feature com base no identificador único da tarefa.

Por exemplo

![Exemplo Jira 01](https://github.com/owInteractive/OW-GIT-workflow/raw/master/media/jira-01.jpg "Exemplo Jira 01")

Tem o identificador **OI-156** Onde **OI** é o projeto **OW Interactive** é o número da tarefa em sequência.

Portando iremos criar uma feature com o nome do identificador

```git flow feature start OI-156```

> Caso você não tenha familiaridade com a linha de comando, você pode usar o [Source Tree](https://www.sourcetreeapp.com/), [Gitkraken](https://www.gitkraken.com/), [Git Tower](https://www.git-tower.com/mac) e etc, a maiorias desse programas já tem uma integração com o Gitflow portanto todos esses passos podem ser feitos por ele tudo de forma visualmente.

Feito isso, você já tenha desempenhado o que foi pedido, e finalizado as alterações no código.