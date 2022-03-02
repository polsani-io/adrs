# ADRs

Registros de Decisões Arquiteturais, ou Architecture Decision Records ou ainda simplismente ADRs, são documentos que registram as decisões importantes envolvendo a "vida" do software ou projeto, como por exemplo qual foi a linguagem de programação escolhida, qual a ferramenta para gerenciamento de configurações, utilizar containers ou não, entre outros registros que julgamos ser úteis de serem documentados para a prosperidade do projeto e/ou da companhia.

Muitas vezes nos deparamos com projetos em andamento e nos perguntamos: quem foi que escolheu essa ferramenta? Quem foi que escolheu essa linguagem? Será que não sabem que poderiam ter solucionado isso dessa outra maneira muito mais simples? Quando isso acontece ficamos indignados pois para nós é muito claro a vantagem de X sobre Y e é um absurdo não terem feito de outra maneira. O ponto é, nem sempre sabemos do contexto todo, os motivos que levaram a adotar aquela estratégia ou as restrições do projeto tanto em tecnologia como em infra-estrutura por exemplo. Sempre existe um contexto a ser observado e as ADRs nos dão esse contexto em momentos que as pessoas que iniciaram o projeto nem sempre continuam na companhia, ou até mesmo nós não nos recordamos mais o porque fizemos daquela forma.

Normalmente utilizamos arquivos de texto (no caso estamos utilizando arquivos no formato __markdown__) e os guardamos junto com o projeto, ou até mesmo em um projeto centralizado de documentações, quando essas decisões abordam padrão da companhia e não somente um projeto ou aplicação em específico. Esses arquivos são normalmente curtos e descrevem qual a decisão foi tomada tendo comumente as seções:

* Título ou nome da ADR, sobre o que ela se trata
* Contexto, falando sobre o problema, variáveis envolvidas, restrições do projeto, custos,  tudo o que for pertinente para contextualizar a descrição.
* Decisão, descrevendo qual foi a abordagem escolhida
* Status, indicando se está aceita, depreciada ou apenas proposta
* Consequências, mostrando o que deve ser esperado a partir dessa decisão, mostrando pontos positivos e negativos da abordagem escolhida

Podemos incrementar as ADRs acrescentando as opções que foram cogitadas mas não foram aceitas como solução, juntamente com seus pontos fortes e fracos.

__Mas para o que devemos ter ADRs?__

Podemos documentar como ADR quaisquer tipos de decisões, mas para diminiuir a quantidade e aumentar a velocidade de entrega, não documentamos tudo, apenas definições de padrões utilizados e ferramentas, como utilizar um message broker como o RabbitMQ ou um PubSub do Redis por exemplo.

Itens padrões da linguagem, como padrões de nome de variáveis, onde cada linguagem tem seu próprio padrão, normalmente não são documentados, acredita-se no bom senso do time para que não precisemos documentar tão no detalher até esse ponto.


## Ferramentas

Para ajudar com a geração e gestão das ADRs, podemos utilizar ferramentas, no caso CLIs para isso, seguem duas sugestões que são interessantes:

* [Command-line tools for working with Architecture Decision Records](https://github.com/npryce/adr-tools)
* [Command line tools with python by Victor Sluiter](https://bitbucket.org/tinkerer_/adr-tools-python/src/master/)

## Templates e exemplos

Esse projeto contém templates e exemplos para auxiliar você a produzir suas próprias ADRs. Cada um dos exemplos foi montado em um template diferente, já para demonstrar no mundo real, como utilizar cada um dos template, alguns mais detalhados, outros mais objetivos, mas todos visam registrar a história das decisões envolvendo o software ou projeto.

Seguem os créditos abaixo de onde foram encontrados os templates (todos os templates foram encontrados em inglês e sua tradução/adaptação para o português foi feita por nós):

* [Template](https://github.com/joelparkerhenderson/architecture-decision-record/blob/main/templates/decision-record-template-madr/index.md) por MADR
* [Template](https://github.com/joelparkerhenderson/architecture-decision-record/blob/main/templates/decision-record-template-by-michael-nygard/index.md) por Michael Nygard
* [Template](https://github.com/joelparkerhenderson/architecture-decision-record/blob/main/templates/decision-record-template-by-jeff-tyree-and-art-akerman/index.md) por Jeff Tyree and Art Akerman
* [Template](https://github.com/pmerson/ADR-template) por Paulo Merson