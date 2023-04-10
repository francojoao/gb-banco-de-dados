---
description: >-
  Além de números, não raramente pode surgir a necessidade de armazenar dados no
  formato de strings no banco de dados. Para isto, no MySQL, usamos alguns dos
  tipos de dados apresentados nesta página.
layout: editorial
---

# 🔠 Tipos textuais

Os principais tipos de dados textuais – isto é, no formato de _strings_, cadeiras de caracteres –, são <mark style="color:blue;">`CHAR`</mark>, <mark style="color:blue;">`VARCHAR`</mark>, <mark style="color:blue;">`BINARY`</mark>, <mark style="color:blue;">`VARBINARY`</mark>, <mark style="color:blue;">`BLOB`</mark>, <mark style="color:blue;">`TEXT`</mark>, <mark style="color:blue;">`ENUM`</mark> e <mark style="color:blue;">`SET`</mark>.&#x20;

Quando definimos uma coluna dos tipos <mark style="color:blue;">`CHAR`</mark> e <mark style="color:blue;">`VARCHAR`</mark>, precisamos passar um argumento que corresponde ao tamanho máximo de caracteres que tal coluna poderá armazenar. Um exemplo disso é: <mark style="color:blue;">`CHAR(20)`</mark> suporta até 20 caracteres, incluindo letras, números e caracteres especiais. No caso do tipo <mark style="color:blue;">`CHAR`</mark>, é possível passar um número de 0 a 255, enquanto no tipo <mark style="color:blue;">`VARCHAR`</mark> este número vai até 65535.

{% hint style="info" %}
#### <mark style="color:blue;">**Curiosidade**</mark>

[Qual a utilidade do tipo de coluna <mark style="color:blue;">`VARCHAR(0)`</mark>?](https://pt.stackoverflow.com/questions/191501/qual-a-utilidade-do-tipo-de-coluna-varchar0)
{% endhint %}

## Tipo `CHAR` ou `VARCHAR`: quando usar?

Certamente, em algum momento você vai se questionar quando usar o tipo <mark style="color:blue;">`CHAR`</mark> ou <mark style="color:blue;">`VARCHAR`</mark>. Neste caso, qual seria então a diferença entre os dois tipos? Simples: enquanto o primeiro tem tamanho fixo, o segundo tem tamanho variável, [~~como o próprio "VAR" antes do CHAR sugere~~](#user-content-fn-1)[^1].&#x20;

<table data-card-size="large" data-column-title-hidden data-view="cards"><thead><tr><th>Tipo</th><th>Descrição</th><th>Tamanho</th></tr></thead><tbody><tr><td><mark style="color:blue;"><code>CHAR</code></mark></td><td><em>String</em> de tamanho fixo, pode conter letras, números e caracteres especiais.</td><td>Tamanhos de 0 to 255. O padrão é 1.</td></tr><tr><td><mark style="color:blue;"><code>VARCHAR</code></mark></td><td><em>String</em> de tamanho variável, pode conter letras, números e caracteres especiais.</td><td>Tamanhos de 0 a 65535. O padrão é 1.</td></tr></tbody></table>

Isso quer dizer que uma coluna com tipo <mark style="color:blue;">`CHAR`</mark>, mesmo que a string tenha um tamanho menor que o tamanho máximo especificado na criação da coluna, sempre ocupará o tamanho máximo definido. Já numa coluna com o tipo <mark style="color:blue;">`VARCHAR`</mark>, o tamanho consumido será adaptado pelo banco a partir do valor atribuído à coluna.

<img src="../../.gitbook/assets/file.excalidraw (22).svg" alt="Exemplo considerando uma coluna com conjunto de caracteres de byte único, como latin1" class="gitbook-drawing">

[Segundo a documentação,](https://dev.mysql.com/doc/refman/8.0/en/char.html) as colunas do tipo <mark style="color:blue;">`VARCHAR`</mark> incluem um prefixo de 1 byte – para valores ≤ 255 bytes – ou 2 bytes – para valores > 255 bytes –, que define o número de bytes do valor da coluna, além dos dados.

## Tipos `BINARY` e `VARBINARY`

<table data-card-size="large" data-column-title-hidden data-view="cards"><thead><tr><th>Tipo</th><th>Descrição</th><th>Valores possíveis</th></tr></thead><tbody><tr><td><mark style="color:blue;"><code>BINARY</code></mark></td><td></td><td></td></tr><tr><td><mark style="color:blue;"><code>VARBINARY</code></mark></td><td></td><td></td></tr></tbody></table>

## Tipos `BLOB` e `TEXT`

No MySQL, o tipo BLOB (Binary Large Object) é dividido em quatro tipos, cuja diferença está no tamanho máximo dos valores que uma coluna definida com os respectivos tipos pode armazenar: <mark style="color:blue;">`TINYBLOB`</mark>, <mark style="color:blue;">`BLOB`</mark>, <mark style="color:blue;">`MEDIUMBLOB`</mark> e <mark style="color:blue;">`LONGBLOB`</mark>.

Em termos de tamanho e requisitos de armazenamento, segundo a documentação, o tipo TEXT apresenta subdivisões que são correspondentes às divisões do tipo <mark style="color:blue;">`BLOB`</mark>: <mark style="color:blue;">`TINYTEXT`</mark>, <mark style="color:blue;">`TEXT`</mark>, <mark style="color:blue;">`MEDIUMTEXT`</mark> e <mark style="color:blue;">`LONGTEXT`</mark>.&#x20;

Each BLOB or TEXT value is represented internally by a separately allocated object. This is in contrast to all other data types, for which storage is allocated once per column when the table is opened.

<table data-card-size="large" data-view="cards"><thead><tr><th>Tipos</th><th>Tamanho (em bytes)</th><th data-hidden>Descrição</th></tr></thead><tbody><tr><td><mark style="color:blue;"><code>TINYBLOB</code></mark> | <mark style="color:blue;"><code>TINYTEXT</code></mark></td><td>255</td><td></td></tr><tr><td><mark style="color:blue;"><code>BLOB</code></mark> | <mark style="color:blue;"><code>TEXT</code></mark></td><td>65.535</td><td></td></tr><tr><td><mark style="color:blue;"><code>MEDIUMBLOB</code></mark> | <mark style="color:blue;"><code>MEDIUMTEXT</code></mark></td><td>16.777.215</td><td></td></tr><tr><td><mark style="color:blue;"><code>LONGBLOB</code></mark> | <mark style="color:blue;"><code>LONGTEXT</code></mark></td><td>4.294.967.295</td><td></td></tr></tbody></table>

Mas se os tipos <mark style="color:blue;">`BLOB`</mark> e <mark style="color:blue;">`TEXT`</mark> (e as variações citadas acima) têm o mesmo tamanho e são tipos de strings, o que então eles têm de diferentes?&#x20;

As colunas com tipos <mark style="color:blue;">`BLOB`</mark> "são tratadas como _strings_ binárias ([_byte strings_](#user-content-fn-2)[^2])", de modo que comparações e ordenação são feitos com base nos valores numéricos dos bytes nos valores das colunas.&#x20;

Colunas com tipos <mark style="color:blue;">`TEXT`</mark>, por sua vez, "são tratadas como _strings_ não binárias, cuja ordenação e comparações" são realizados segundo o agrupamento do conjunto de caracteres.&#x20;

## Tipos `ENUM` e `SET`



## Referências

* [https://pt.stackoverflow.com/questions/214295/qual-a-diferen%C3%A7a-entre-varchar-e-nvarchar](https://pt.stackoverflow.com/questions/214295/qual-a-diferen%C3%A7a-entre-varchar-e-nvarchar)
* MYSQL. 11.3.2 The CHAR and VARCHAR Types. Disponível em: [https://dev.mysql.com/doc/refman/8.0/en/char.html](https://dev.mysql.com/doc/refman/8.0/en/char.html)
* 11.3.4 The BLOB and TEXT Types [https://dev.mysql.com/doc/refman/8.0/en/blob.html](https://dev.mysql.com/doc/refman/8.0/en/blob.html)
* [https://dev.mysql.com/doc/refman/8.0/en/string-types.html](https://dev.mysql.com/doc/refman/8.0/en/string-types.html)
* [https://dev.mysql.com/doc/refman/8.0/en/storage-requirements.html#data-types-storage-reqs-strings](https://dev.mysql.com/doc/refman/8.0/en/storage-requirements.html#data-types-storage-reqs-strings)

[^1]: Hey, Mr. Obvious!&#x20;

    Quem poderia imaginar, né?

[^2]: 
