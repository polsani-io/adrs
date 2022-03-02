# ADR 003: Utilizar o padrão CQRS
Temos uma arquitetura de microsserviços com vários serviços REST que precisariam ler e gravar dados.
Às vezes, é difícil projetar esses serviços para executar ambas as tarefas com eficiência.
No sistema Farmacy Food, o design das gravações (comandos) está principalmente preocupado com a integridade dos dados e regras de negócio, enquanto que o design das leituras (consultas) tem o desempenho (tempo de resposta) como requisito fundamental.

## Decisão
Usaremos o [padrão CQRS](https://udidahan.com/2009/12/09/clarified-cqrs/) aplicado a microsserviços com este design:
- um serviço implantado de forma independente cuida das consultas. Ele lê dados de uma *__view__* de consulta otimizada para leituras de dados. ("Otimizado" significa usar tecnologias e técnicas de banco de dados que favorecem o desempenho, como: NoSQL, visualização desnormalizada, cache de memória, fragmentação, replicação.)
- um serviço implantado de forma independente cuida dos comandos. Pode ser um serviço REST que recebe comandos POST ou um serviço reativo que assina um tópico pub-sub e recebe mensagens que atualizam o banco de dados principal para o escopo desse serviço.
- um componente de lote (exemplo: tarefa cron no kubernetes ou lógica ativada por eventos acionados pelo banco de dados) sincroniza os dados entre o banco de dados principal e as __*views*__ de consulta. A frequência de sincronização de dados varia - pode ser baseada em gatilho, a cada 5 minutos, a cada hora, ..., uma vez por dia, etc.

Em nosso design, usamos CQRS para:
- Inventário
- Pedidos
- Inscrição

## Justificativa
Esperamos que o aplicativo emita muito mais solicitações de consulta do que comandos. Por exemplo, o inventário é verificado em muitas operações de clientes, como olhar para um item de refeição do catálogo.
O [padrão CQRS](https://udidahan.com/2009/12/09/clarified-cqrs/) é usado para abordar o desempenho (tempo de resposta) como requisito das consultas.

## Status
Proposta

## Consequências
- O padrão CQRS usa replicação de dados para visualizações de consulta e, portanto, *consistência eventual*. Portanto, os serviços de consulta podem
 operar em dados obsoletos (durante o intervalo entre a sincronização de dados do banco de dados mestre e a visualização de consulta).
- Necessidade de monitorar as tarefas de sincronização de dados, com notificação e ação adequada em caso de falha.