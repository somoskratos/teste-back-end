# Teste para desenvolvedor Back-end

## Por que trabalhar no Kratos?

O Kratos é uma Startup que nasceu em Campo Grande/MS e oferece um sistema de gestão empresarial. Nós entregamos aos nossos clientes um sistema e a contabilidade em um só lugar.

Quer conhecer mais sobre a empresa? http://somoskratos.com.br/

## Sobre a vaga

Estamos à procura do nosso novo desenvolvedor back-end. O desenvolvedor em seu dia a dia irá trabalhar junto com a equipe na refatoração de algumas rotinas do sistema e desenvolvimento de novos módulos. 

## Requisitos

* Ter disponibilidade para trabalhar em Campo Grande/MS.
* Conhecer as seguintes tecnologias:
	* Java
	* Framework Spring
	* Javascript
	* GIT
* Conhecer metodologias ágeis.

## Conhecimento desejável
* Jasper Reports
* HTML/CSS
* AngularJS
* Primefaces

## Tecnologias/Padrões para o desafio

É altamente recomendado a utilização das seguintes tecnologias/padrões:
* Java
* Framework Spring

Não entende/conhece de algumas das tecnologias descritas acima? Não tem problema. Você pode submeter o seu projeto em qualquer tecnologia. Porém projetos que utilizem as tecnologias acima terão pontuações maiores.

## Quais são as etapas para participar do processo?
**ATENÇÃO: O PRAZO SE ENCERRA DIA 18/07/2018** :running:
* Responda nosso [formulário](https://bit.ly/vaga-back-end-kratos).
* Faça um [fork]() desse projeto em sua conta do GitHub.
* Implemente o desafio proposto abaixo.
* Faça um push para seu repositório com o desafio implementado.
* Envie um email para (vagas@somoskratos.com.br) com a URL do seu fork avisando que você concluiu o projeto.

## O Desafio:

Você deverá criar uma **API REST** que receba uma lista chamada **itens** no formato **json** no *body* da sua requisição HTTP, conforme descrito abaixo:
```json
{
	"itens": [{
		"codigo": "COD01",
		"descricao": "Descrição do item",
		"valorUnitario": 1.50,
		"quantidade": 3,
		"tributos": {
			"ICMS": {
				"baseDeCalculo": 0.00,
				"fatorDeReducaoDaBaseDeCalculo": 58.824,
				"aliquota": 17.00,
				"valorICMS": 0.00
			}
		}
	}]
}
```
Note que cada produto enviado à API possui os campos *baseDeCalculo* e *valorICMS* dentro do atributo **tributos** com o valor igual a zero, estes serão os campos a serem calculados. 

A sua API deverá calcular a tributação deste item conforme as regras de tributação do grupo de ICMS com código de tributação do grupo 20 e retornar os impostos calculados.

*Info: O Grupo de ICMS 20 é o grupo que calcula os tributos com redução na base de cálculo.* 

**Descrição dos campos de ICMS:**
* Base de cálculo: Valor utilizado como base para o cálculo do valor do ICMS. 
* Fator de redução da base de cálculo: Percentual na qual a base de cálculo será reduzida. 
* Alíquota: Percentual do imposto a ser aplicado sobre a base de cálculo.
* Valor do ICMS: Valor total do imposto ICMS a ser aplicado.

### Valores a serem calculados:
#### Base de cálculo(*baseDeCalculo*)
A base de cálculo normalmente é o valor total do item (quantidade multiplicada pelo valor unitário). Porém quando o produto tem redução na base de cálculo (que é o caso deste desafio) o valor é reduzido. Para calcular a base de cálculo com redução leva-se em consideração o valor total do item porém subtraído o *valor de redução de base de cálculo*. O *valor de redução de base de cálculo* é calculado multiplicando-se o valor total do item pelo seu fator de redução (atributo descrito neste desafio como *fatorDeReducaoDaBaseDeCalculo*).

Você também pode consultar na internet como calcular esta redução.

#### Valor do ICMS (*valorICMS*)
O valor do ICMS é calculado pela simples multiplicação da base de cálculo obtida anteriormente multiplicado pela alíquota do ICMS. 
****

Para o exemplo apresentado a resposta seria a seguinte:

```json
{
	"itens": [{
		"codigo": "COD01",
		"descricao": "Descrição do item",
		"valorUnitario": 1.50,
		"quantidade": 3,
		"tributos": {
			"ICMS": {
				"baseDeCalculo": 1.85,
				"fatorDeReducaoDaBaseDeCalculo": 58.824,
				"aliquota": 17.00,
				"valorICMS": 0.31
			}
		}
	}]
}
```
Os valores devem ser retornados com somente duas casas decimais. 

## API REST
##### Request
```bash
 POST http://localhost:8080/rest/icms/ 
```


**Retornos Possíveis**

Código | Resposta
------------ | -------------
`200 (OK)` | `Objeto json com a tributação calculada ` 
`400 (Bad request)` | `Ocorreu um erro desconhecido ao calcular a tributação.`
`400 (Bad request)` | `Os valores informados não são válidos.`


## Critérios de avaliação:
Entre os critérios de avaliação estão:
* Usabilidade.
* Organização do código.
* Performance do código.
* Documentação do código.
* Boas práticas de desenvolvimento.
* Arquitetura do projeto.
* Documentação do projeto (README)

## Restou alguma dúvida?
Você pode enviar um email para: vagas@somoskratos.com.br
