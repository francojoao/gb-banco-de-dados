---
layout: editorial
---

# 🔢 Tipos numéricos

## Tipos numéricos inteiros

O MySQL, [de acordo com a documentação](https://dev.mysql.com/doc/refman/8.0/en/integer-types.html), suportam os padrões SQL <mark style="color:blue;">`INTEGER`</mark> (<mark style="color:blue;">`INT`</mark> é um sinônimo para <mark style="color:blue;">`INTEGER`</mark>) e <mark style="color:blue;">`SMALLINT`</mark> e oferecem, ainda os tipos <mark style="color:blue;">`TINYINT`</mark>, <mark style="color:blue;">`MEDIUMINT`</mark> e <mark style="color:blue;">`BIGINT`</mark>, cujas características são descritas na tabela abaixo, adaptada da documentação oficial. Nota-se que os valores mínimos para o tipo numéricos <mark style="color:blue;">`UNSIGNED`</mark> – sem sinal, ou seja, positivos – tem como valor mínimo 0. &#x20;

<table><thead><tr><th>Tipo</th><th data-type="number">Tamanho (em bytes)</th><th>Valores mínimo e máximo signed</th><th>Valores mínimo e máximo unsigned</th></tr></thead><tbody><tr><td><mark style="color:blue;"><code>TINYINT</code></mark></td><td>1</td><td>-128 a 127</td><td>0 a 255</td></tr><tr><td><mark style="color:blue;"><code>SMALLINT</code></mark></td><td>2</td><td>-32768 a 32767</td><td>0 a 65535</td></tr><tr><td><mark style="color:blue;"><code>MEDIUMINT</code></mark></td><td>3</td><td>-8388608 a 8388607 </td><td>0 a 16777215</td></tr><tr><td><mark style="color:blue;"><code>INT</code></mark> ou <mark style="color:blue;"><code>INTEGER</code></mark></td><td>4</td><td>-2147483648 a 2147483647</td><td>0 a 4294967295</td></tr><tr><td><mark style="color:blue;"><code>BIGINT</code></mark></td><td>8</td><td>-2^63 a 2^63 - 1</td><td>0 a 2^64 - 1</td></tr></tbody></table>

Existem também os tipos <mark style="color:blue;">`BOOL`</mark> e o sinônimo <mark style="color:blue;">`BOOLEAN`</mark>, que são armazenados como zero, representando o valor falso, e qualquer valor diferente pode ser considerado verdadeiro.&#x20;

{% hint style="warning" %}
_<mark style="color:orange;">**Spoiler alert**</mark>_<mark style="color:orange;">**:**</mark>&#x20;

Usando _nosso_ querido [MySQL Workbench](https://www.mysql.com/products/workbench/), você vai observar que, ao elaborar um diagrama EER, quando tentar inserir uma coluna do tipo <mark style="color:blue;">`BOOL`</mark> ou <mark style="color:blue;">`BOOLEAN`</mark>, a ferramenta mudará esse valor para o tipo <mark style="color:blue;">`TINYINT`</mark>.&#x20;
{% endhint %}

Além dos tipos apresentados acima, temos também o tipo <mark style="color:blue;">`BIT`</mark>, compatíveis com _engines_ de armazenamento [`MyISAM`](https://dev.mysql.com/doc/refman/8.0/en/myisam-storage-engine.html), [`MEMORY`](https://dev.mysql.com/doc/refman/8.0/en/memory-storage-engine.html), [`InnoDB`](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html) e [`NDB`](https://dev.mysql.com/doc/refman/8.0/en/mysql-cluster.html), segundo a documentação do MySQL; colunas deste tipo armazenam valores binários, no qual podemos passar como argumento um número de 1 (que, por sinal, é o valor padrão) a 64, que representa o tamanho.

{% hint style="info" %}
<mark style="color:blue;">**Curiosidade**</mark>

Eu estava arrumando isso aqui e me bateu uma curiosidade: se existe um tipo <mark style="color:blue;">`BIT`</mark>, não seria mais coerente, até por economia de armazenamento, utilizar este tipo em vez do tipo <mark style="color:blue;">`TINYINT`</mark> para representar os valores binários verdadeiro/falso?

Encontrei [essa discussão no Stack Overflow](https://pt.stackoverflow.com/questions/108842/bit1-versus-tinyint1-para-valores-booleanos) e penso que é algo interessante a compartilhar com os também curiosos. Lá, eu encontrei uma resposta que resume um pouco essa pergunta: "O tamanho mínimo de armazenamento de uma coluna do tipo <mark style="color:blue;">`BIT`</mark> é 1 byte, mesmo que só precise de 1 bit".&#x20;

Recomendo a leitura/participação no tópico.
{% endhint %}

### Propriedades numéricas ZEROFILL (ZF) e UNSIGNED (UN)

A propriedade numérica <mark style="color:blue;">`ZEROFILL`</mark>, no MySQL, preenche uma coluna com zeros à esquerda do número cujo dado do tipo inteiro tem um tamanho <mark style="color:blue;">`N`</mark> especificado -- <mark style="color:blue;">`INT(N)`</mark> --, seguindo a palavra reservada <mark style="color:blue;">`INT`</mark>.&#x20;

<img src="../../.gitbook/assets/file.excalidraw (12).svg" alt="" class="gitbook-drawing">

{% hint style="warning" %}
<mark style="color:orange;">**Nota:**</mark>

A partir do MySQL 8.0.17, a propriedade <mark style="color:blue;">`ZEROFILL`</mark> e o atributo de largura de exibição para tipos de dados inteiros estão obsoletos, sendo necessário o uso de outros artifícios para produzir os mesmos efeitos.
{% endhint %}

Importante pontuar que o atributo <mark style="color:blue;">`ZEROFILL`</mark>, uma vez utilizado, implica o uso automático de outra propriedade: <mark style="color:blue;">`UNSIGNED`</mark>.

<img src="../../.gitbook/assets/file.excalidraw (36).svg" alt="" class="gitbook-drawing">

A propriedade <mark style="color:blue;">`UNSIGNED`</mark>, [segundo a documentação](https://dev.mysql.com/doc/refman/8.0/en/numeric-type-attributes.html), "pode ser usada para permitir apenas números não negativos numa coluna ou quando você precisa de um conjunto muito maior de números para uma coluna", uma vez que, como mostra a tabela 1, um inteiro <mark style="color:blue;">`SIGNED`</mark> – propriedade padrão – consegue armazenar números entre -2147483648 e 2147483647, enquanto, com a propriedade  <mark style="color:blue;">`UNSIGNED`</mark>, esse intervalo vai de 0 a 4294967295.

## Tipos numéricos de ponto fixo e ponto flutuante

No MySQL, temos um tipo numérico de ponto fixo, com valores exatos, representado pelo tipo <mark style="color:blue;">`DECIMAL`</mark>, que tem como sinônimos os tipos <mark style="color:blue;">`DEC`</mark> e <mark style="color:blue;">`FIXED`</mark>. Há, ainda, o tipo <mark style="color:blue;">`NUMERIC`</mark>, que no MySQL funciona da mesma maneira que o tipo <mark style="color:blue;">`DECIMAL`</mark>, [de acordo com a documentação](https://dev.mysql.com/doc/refman/8.0/en/fixed-point-types.html), e "esses tipos são usados quanto é importante preservar a precisão exata" do dado a ser armazenado.

<img src="../../.gitbook/assets/file.excalidraw (33).svg" alt="" class="gitbook-drawing">

Os tipos <mark style="color:blue;">`FLOAT`</mark> e <mark style="color:blue;">`DOUBLE`</mark> correspondem a dados numéricos aproximados, que podem ser de precisão simples ou dupla. Para o tipo de precisão simples, <mark style="color:blue;">`FLOAT`</mark>, [conforme a documentação](https://dev.mysql.com/doc/refman/8.0/en/floating-point-types.html) do MySQL, opcionalmente, é possível definir a precisão **em bits** (<mark style="color:blue;">`p`</mark>) na sequência da palavra-chave: <mark style="color:blue;">`FLOAT(p)`</mark>, seguindo o padrão SQL. Para efeitos práticos, isso permite que uma coluna do tipo <mark style="color:blue;">`FLOAT`</mark> tenha dupla precisão, ou seja, funcione como uma coluna do tipo <mark style="color:blue;">`DOUBLE`</mark>.

<img src="../../.gitbook/assets/file.excalidraw (34).svg" alt="" class="gitbook-drawing">

## Referências

* MONTEIRO, Lucas. MySQL — Tipos de dados: Introdução e dados numéricos (1 de 3). Disponível em: [https://medium.com/mandabugs/mysql-tipos-de-dados-introdu%C3%A7%C3%A3o-e-dados-num%C3%A9ricos-1-de-3-a6e48fb5e1d3](https://medium.com/mandabugs/mysql-tipos-de-dados-introdu%C3%A7%C3%A3o-e-dados-num%C3%A9ricos-1-de-3-a6e48fb5e1d3). Acesso em 06 Abr. 2023.
* MySQL Data Types. Disponível em: [https://dev.mysql.com/doc/refman/8.0/en/data-types.html](https://dev.mysql.com/doc/refman/8.0/en/data-types.html).  Acesso em:&#x20;
* [https://dev.mysql.com/doc/refman/8.0/en/floating-point-types.html](https://dev.mysql.com/doc/refman/8.0/en/floating-point-types.html)
* [https://dev.mysql.com/doc/refman/8.0/en/bit-type.html](https://dev.mysql.com/doc/refman/8.0/en/bit-type.html)
* MySQL Numeric type attributes. Disponível em: [https://dev.mysql.com/doc/refman/8.0/en/numeric-type-attributes.html](https://dev.mysql.com/doc/refman/8.0/en/numeric-type-attributes.html). Acesso em:&#x20;
* [https://pt.stackoverflow.com/questions/108842/bit1-versus-tinyint1-para-valores-booleanos](https://pt.stackoverflow.com/questions/108842/bit1-versus-tinyint1-para-valores-booleanos).
