# Teste para desenvolvedor Back-end

## Por que trabalhar no Kratos?

O Kratos é uma Startup que nasceu em Campo Grande/MS e oferece um sistema de gestão empresarial. Nós entregamos aos nossos clientes um sistema e a contabilidade em um só lugar.

Quer conhecer mais sobre a empresa? http://somoskratos.com.br/

## Sobre a vaga

Estamos à procura do nosso novo desenvolvedor back-end pleno/senior para inovar na área de contabilidade.

O desenvolvedor em seu dia a dia irá trabalhar junto com a equipe na criação de novas funcionalidades e refatoração de algumas rotinas do sistema desenvolvendo novos módulos.

Este desenvolvedor irá compor um ambiente bem tranquilo, nossa regra é: liberdade com responsabilidade.

Se você se enquadra nessa idéia os requisitos são: 

## Requisitos
* Ter disponibilidade para trabalhar em Campo Grande/MS.
* Ter excelente comunicação.
* Conhecer metodologias ágeis.
* Ter experiência nos seguintes itens:
	* Java 8+
  * Spring Cloud, Spring Boot e Spring Data
  * Microserviços em Java
  * Dockerização de aplicações em Java
  * Linux Básico
  * Integração e Deploy contínuo
  * Documentação e boas práticas de API's RestFull
  * TDD, DDD e Design Patterns

## Tecnologias para o desafio
* Java 8
* Framework Spring
* Banco de dados (SQL Server, Postgres ou Mysql)
* Circle CI
* Docker / Docker Compose
* Framework de documentação de API (Swagger ou similares)

## O Desafio:

Você deverá criar uma **API REST** que possa cadastrar pessoas, empresas, e associar um sócio a uma empresa. Deve também ser possível consultar a lista de todas as empresas (paginação será um diferencial) e também apenas uma empresa por CNPJ. A consulta de empresas deverá ter algum tipo de mecanismo para cacheamento das informações cadastradas e deve retornar um Json igual o abaixo.

Retorno da consulta da empresa
```json
{
  "id": Long,
  "cnpj": String,
  "email": String,
  "razaoSocial": String,
  "nomeFantasia": String,
  "socios": [Socio],
  "capitalSocial": Numeric
}
```

**O capital social deve ser igual a soma das cotas de todos os sócios**

JSON's de cadastro

Empresa
```json
{
  "cnpj": String,
  "email": String,
  "razaoSocial": String,
  "nomeFantasia": String,
}
```

Pessoa
```json
{
  "cpf": String,
  "email": String,
  "nome": String,
  "sobrenome": String,
}
```

Socio
```json
{
  "empresa": {
    id: Long
  },
  "pessoa": {
    id: Long
  },
  "valorDaCota": Numeric,
}
```

**É importante que as entradas sejam válidadas**

## Como devo entregar o desafio?
* Crie uma branch a partir da branch master deste respositório.
* Implemente o desafio de código
* Configure o circle CI para rodar os testes do projeto
* Faça um push de sua branch com o desafio implementado.
* Crie um pull request para branch master
* Envie um email para (vagas@somoskratos.com.br) com o nome de sua branch informando que você concluiu o projeto.

## Restou alguma dúvida?
Você pode enviar um email para: vagas@somoskratos.com.br
