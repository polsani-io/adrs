# Template de registro de decisão por Jeff Tyree e Art Akerman

Este é o modelo de descrição de decisão de arquitetura publicado em ["Architecture Decisions: Demystifying Architecture" by Jeff Tyree and Art Akerman, Capital One Financial](https://www.utdallas.edu/~chung/SA/zz-Impreso-architecture_decisions-tyree-05.pdf).

**Problema**: Descreva o problema de arquitetura que você está abordando, sem deixar dúvidas sobre por que você está abordando esse problema agora. Seguindo uma abordagem minimalista, trate e documente apenas as questões que precisam ser abordadas em vários pontos do ciclo de vida.

**Decisão**: Indique claramente a direção da arquitetura, ou seja, a posição que você selecionou.

**Status**: O status da decisão, como pendente, decidida ou aprovada.

**Grupo**: Você pode usar um agrupamento simples, como integração, apresentação, dados, etc., para ajudar a organizar o conjunto de decisões. Você também pode usar uma ontologia de arquitetura mais sofisticada, como a de John Kyaruzi e Jan van Katwijk, que inclui categorias mais abstratas, como evento, calendário e local. Por exemplo, usando esta ontologia, você agruparia decisões que tratam de ocorrências em que o sistema requer informações sob evento.

**Suposições**: Descreva claramente as premissas subjacentes no ambiente em que você está tomando a decisão: custo, cronograma, tecnologia e assim por diante. Observe que as restrições ambientais (como padrões de tecnologia aceitos, arquitetura corporativa, padrões comumente empregados e assim por diante) podem limitar as alternativas para considerar.

**Restrições**: Liste quaisquer restrições adicionais ao ambiente que a alternativa escolhida (a decisão) possa representar.

**Posições**: Liste as posições (opções ou alternativas viáveis) que você considerou. Isso geralmente exige longas explicações, às vezes até modelos e diagramas. Esta não é uma lista exaustiva. No entanto, você não quer ouvir a pergunta "Você pensou em...?" durante uma revisão final; isso leva à perda de credibilidade e questionamento de outras decisões arquiteturais. Esta seção também ajuda a garantir que você ouviu as opiniões de outras pessoas; declarar explicitamente outras opiniões ajuda a unir seus defensores em sua decisão.

**Argumento**: Descreva por que você selecionou uma posição, incluindo itens como custo de implementação, custo total de propriedade, tempo de lançamento no mercado e disponibilidade de recursos de desenvolvimento necessários. Isso é provavelmente tão importante quanto a decisão em si.

**Implicações**: Uma decisão vem com muitas implicações, como denota o metamodelo REMAP. Por exemplo, uma decisão pode introduzir a necessidade de tomar outras decisões, criar novos requisitos ou modificar requisitos existentes; impõem restrições adicionais ao meio ambiente; exigir renegociação de escopo ou cronograma com clientes; ou exigir treinamento adicional de pessoal. Entender e declarar claramente as implicações de sua decisão pode ser muito eficaz para obter adesão e criar um roteiro para a execução da arquitetura.

**Decisões relacionadas**: É óbvio que muitas decisões estão relacionadas; você pode listá-los aqui. No entanto, descobrimos que, na prática, uma matriz de rastreabilidade, árvores de decisão ou metamodelos são mais úteis. Os metamodelos são úteis para mostrar relacionamentos complexos em diagramas (como os modelos Rose).

**Requisitos relacionados**: As decisões devem ser orientadas para os negócios. Para mostrar responsabilidade, mapeie explicitamente suas decisões para os objetivos ou requisitos. Você pode enumerar esses requisitos relacionados aqui, mas achamos mais conveniente fazer referência a uma matriz de rastreabilidade. Você pode avaliar a contribuição de cada decisão de arquitetura para atender a cada requisito e, em seguida, avaliar quão bem o requisito é atendido em todas as decisões. Se uma decisão não contribuir para atender a um requisito, não tome essa decisão.

**Artefatos relacionados**: Lista dos documentos de arquitetura relacionados, design ou documentos de escopo que essa decisão impacta.

**Princípios relacionados**: Se a empresa tiver um conjunto de princípios acordado, certifique-se de que a decisão seja consistente com um ou mais deles. Isso ajuda a garantir o alinhamento entre domínios ou sistemas.

**Observações**: Como o processo de tomada de decisão pode levar semanas, achamos útil registrar anotações e problemas que a equipe discute durante o processo de socialização.