# Lab 4 — Dividir o Monólito

Template de partida para o **Lab 4** de Distributed Systems 2026/27.

Vais dividir a aplicação única do Lab 3 em dois serviços com deploy independente, cada um com a sua base de dados, a chamarem-se um ao outro com clientes `@HttpExchange`.

## A usar este template

Carrega em **Use this template → Create a new repository** no GitHub. Dá-lhe o nome
`lab-04-store-microservices-aXXXXXXXX` com o teu número de aluno.
Não faças fork, e não clones este repositório diretamente — precisas do teu próprio histórico.

## O que está aqui

O scaffolding: o POM com todas as dependências de que o lab precisa, a estrutura de packages,
a configuração, e a preparação do container. Constrói e arranca tal como está.

## O que não está aqui

As entidades, repositories, services, controllers e — o ponto do lab — as interfaces de cliente `@HttpExchange` e a sua configuração. O package `client` existe e está vazio nos dois módulos.

Isso é deliberado. Um template é um ponto de partida, não a resposta.

## A correr

```bash
cp .env.example .env
docker compose up --build
```

## Versões

Java 25, Spring Boot 4.1.0, Maven 3.9.16. Vê
[Toolchain e versões](https://github.com/DistributedSystems-Lusofona27/course-docs/blob/main/toolchain-and-versions.md)
se algo não resolver — a maior parte dos problemas de versões nesta cadeira vêm de seguir
um tutorial escrito para o Spring Boot 3.
