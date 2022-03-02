# Nomenclatura de APIs

## Status

Aceita

## Contexto

Para padronizar e tornar mais legível e fácil identificar os recursos e sub-recursos, incluindo as intenções de alterar o estado desses recursos, é necessária uma estratégia para nomeá-los.

## Decisão

Para nomear uma API, use kebab case.

A fim de tornar o URI mais legível e utilizar um padrão amplamente utilizado no mercado.

Exemplo:
```
https://url-minha-aplicacao/api/v1/meu-recurso

https://url-minha-aplicacao/api/v1/meu-recurso/{id}/meu-sub-recurso
```

## Consequências

### Consequências Positivas

* Mais legível
* Tendência de mercado
* Digitação fluente (não pressionando mais de uma tecla)

### Consequências negativas

* URIs longas podem ser estranhas