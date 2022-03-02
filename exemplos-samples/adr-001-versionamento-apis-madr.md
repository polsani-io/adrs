# Versionamento de APIs

* Situação: __Aceito__
* Decisores: Henrique Polsani
* Data: 04-02-2022

História técnica: [Task-10001](http://minha-ferramenta-gerenciamento-tarefas-url/link-task)

---

## Contexto e Declaração do Problema

Para permitir que a aplicação evolua, muitas vezes é necessário quebrar o contrato de comunicação estabelecido em uma API.

Para permitir a coexistência da versão antiga e uma nova versão de uma API, é necessária uma estratégia de versionamento para minimizar os possíveis impactos.

---

## Direcionadores de decisão

* Tendência de mercado (familiar para novos colaboradores)
* Habilidade e conhecimento da equipe atual
* Facilidade de implementação de cache

---

## Opções consideradas

* Versionamento na __URI__
* Usar um __Cabeçalho HTTP personalizado__
* Usar o cabeçalho __Accept__
* Versionamento através de __Query String__
* Sem versionamento

---

## Resultado da decisão

Para APIs de versionamento, use-o por meio do URI Path. Este é um padrão amplamente utilizado no mercado.

Para identificar que o aplicativo é uma API, usaremos o indicador ```/api``` no URI Path (verifique [adr-002-nomeando-apis](https://github.com/polsani-io/adrs/blob/main/exemplos-samples/adr-002-nomeando-apis.md)), apenas usando a versão da API como versão __*MAJOR*__ com o prefixo ```v``` : ```v1```, ```v2```, ```v3```.

As APIs são versionadas no nível do recurso, onde se houver necessidade de um versionamento, todo o recurso é versionado, como todas as requisições relacionadas a este recurso (GET, POST, PUT, DELETE, PATCH, etc).

Exemplo:
```
https://url-minha-aplicacao/api/v1/meu-recurso
```

O cenário para a versão de uma API é: uma alteração importante com JSON retornado ou solicitado. Somente cenários em que a alteração não é compatível com o contrato atual devem causar um controle de versão da API.

### __Consequências Positivas__

* Mais familiar para desenvolvedores e consumidores
* Muito simples de entender e implementar
* Atualmente é a forma de versionamento mais utilizada pela equipe de desenvolvimento
* Muito simples de implementar uma estratégia de cache

### __Consequências negativas__

* Viola os princípios REST em que apenas uma única URI deve representar um recurso

---

## Prós e Contras das Opções

### Usar um __Cabeçalho HTTP personalizado__

* Bom, porque mantém os princípios REST onde apenas uma única URI deve representar um recurso
* Ruim, pois precisa de uma estratégia de cache específica
* Ruim, pois não é uma tendência de mercado
* Ruim, pois é algo intrínseco da própria empresa

Exemplo:
```
Versao-Api: v1
[GET] https://url-minha-aplicacao/api/meu-recurso
```

### Usar o cabeçalho __Accept__

* Bom, porque mantém os princípios REST onde apenas uma única URI deve representar um recurso
* Ruim, pois não é uma tendência de mercado
* Ruim, pois é um pouco confuso para quem nunca usou

Exemplo:
```
Accept: application/my-company.my-app.resource-v1+json
[GET] https://url-minha-aplicacao/api/meu-recurso
```

### Versionamento através de __Query String__

* Bom, porque é muito simples de entender e implementar
* Bom, porque é simples implementar uma estratégia de cache
* Ruim, pois não é uma tendência de mercado

Exemplo:
```
[GET] https://url-minha-aplicacao/api/meu-recurso?versao=v1
```

### Sem versionamento

* Bom, porque força o uso do HATEOAS como prática REST para tornar a comunicação mais clara
* Bom, porque mantém os princípios REST onde apenas uma única URI deve representar um recurso
* Ruim, pois não é uma tendência de mercado
* Ruim, porque não é familiar para a equipe de desenvolvimento

Exemplo:
```
https://url-minha-aplicacao/api/meu-recurso
```

---

## Links

* Referenciado [adr-002-api-naming](https://github.com/polsani-io/adrs/blob/main/exemplos-samples/en-US/adr-002-api-naming.md)