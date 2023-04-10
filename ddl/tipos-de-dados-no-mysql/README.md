# 🧮 Tipos de Dados no MySQL

[Segundo a documentação](https://dev.mysql.com/doc/refman/8.0/en/numeric-types.html), o MySQL "suporta todos os tipos os tipos de dados padrões da SQL" ([tradução nossa](#user-content-fn-1)[^1]).&#x20;

## Tipos numéricos

<table><thead><tr><th>Tipo</th><th data-type="number">Tamanho (em bytes)</th><th>Valores mínimo e máximo signed</th><th>Valores mínimo e máximo unsigned</th></tr></thead><tbody><tr><td><mark style="color:blue;"><code>TINYINT</code></mark></td><td>1</td><td>-128 a 127</td><td>0 a 255</td></tr><tr><td><mark style="color:blue;"><code>SMALLINT</code></mark></td><td>2</td><td>-32768 a 32767</td><td>0 a 65535</td></tr><tr><td><mark style="color:blue;"><code>MEDIUMINT</code></mark></td><td>3</td><td>-8388608 a 8388607 </td><td>0 a 16777215</td></tr><tr><td><mark style="color:blue;"><code>INT</code></mark> ou <mark style="color:blue;"><code>INTEGER</code></mark></td><td>4</td><td>-2147483648 a 2147483647</td><td>0 a 4294967295</td></tr><tr><td><mark style="color:blue;"><code>BIGINT</code></mark></td><td>8</td><td>-2^63 a 2^63 - 1</td><td>0 a 2^64 - 1</td></tr><tr><td><mark style="color:blue;"><code>DECIMAL</code></mark>, <mark style="color:blue;"><code>DEC</code></mark>, <mark style="color:blue;"><code>FIXED</code></mark>, <mark style="color:blue;"><code>NUMERIC</code></mark></td><td>null</td><td></td><td></td></tr><tr><td><mark style="color:blue;"><code>FLOAT</code></mark></td><td>null</td><td></td><td></td></tr><tr><td><mark style="color:blue;"><code>DOUBLE</code></mark></td><td>null</td><td></td><td></td></tr></tbody></table>

## Textuais

| Tipo                                          | Descrição | Tamanho |
| --------------------------------------------- | --------- | ------- |
| <mark style="color:blue;">`TEXT`</mark>       |           |         |
| <mark style="color:blue;">`TINYTEXT`</mark>   |           |         |
| <mark style="color:blue;">`MEDIUMTEXT`</mark> |           |         |
| <mark style="color:blue;">`LONGTEXT`</mark>   |           |         |
| <mark style="color:blue;">`ENUM`</mark>       |           |         |

| Tipo                                        | Descrição                                                                                                                                  | Tamanho                                      |
| ------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------- |
| <mark style="color:blue;">`CHAR`</mark>     | Pode conter letras, números e caracteres especiais.                                                                                        | <p>Fixo, de 0 to 255. </p><p>Padrão é 1.</p> |
| <mark style="color:blue;">`NCHAR`</mark>    | Forma de indicar que uma coluna do tipo [`CHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html) deve usar algum _charset_ predefinido. | <p>Fixo, de 0 to 255. </p><p>Padrão é 1.</p> |
| <mark style="color:blue;">`VARCHAR`</mark>  | Pode conter letras, números e caracteres especiais.                                                                                        | Variável, de 0 a 65535.                      |
| <mark style="color:blue;">`NVARCHAR`</mark> |                                                                                                                                            | Variável, de 0 a 65535.                      |
| <mark style="color:blue;">`JSON`</mark>     |                                                                                                                                            |                                              |

|                                               |   |   |
| --------------------------------------------- | - | - |
| <mark style="color:blue;">`BINARY`</mark>     |   |   |
| <mark style="color:blue;">`VARBINARY`</mark>  |   |   |
| <mark style="color:blue;">`BLOB`</mark>       |   |   |
| <mark style="color:blue;">`TINYBLOB`</mark>   |   |   |
| <mark style="color:blue;">`MEDIUMBLOB`</mark> |   |   |
| <mark style="color:blue;">`LONGBLOB`</mark>   |   |   |

## Data/Hora

| Tipo                                         | Formato               | Valores permitidos                                                 |
| -------------------------------------------- | --------------------- | ------------------------------------------------------------------ |
| <mark style="color:blue;">`YEAR`</mark>      | 'YYYY'                | <p>0000, </p><p>1901 a 2155</p>                                    |
| <mark style="color:blue;">`DATE`</mark>      | 'YYYY-MM-DD'          | <p>'1000-01-01' a </p><p>'9999-12-31'</p>                          |
| <mark style="color:blue;">`TIME`</mark>      | 'hh:mm:ss'            | <p>'-838:59:59' a</p><p>'838:59:59'</p>                            |
| <mark style="color:blue;">`DATETIME`</mark>  | 'YYYY-MM-DD hh:mm:ss' | <p>'-838:59:59' a</p><p>'838:59:59'</p>                            |
| <mark style="color:blue;">`TIMESTAMP`</mark> | 'YYYY-MM-DD hh:mm:ss' | <p>'1970-01-01 00:00:01' UTC a</p><p>'2038-01-09 03:14:07' UTC</p> |

## Referências

* MONTEIRO, Lucas. MySQL — Tipos de dados: Introdução e dados numéricos (1 de 3). Disponível em: [https://medium.com/mandabugs/mysql-tipos-de-dados-introdu%C3%A7%C3%A3o-e-dados-num%C3%A9ricos-1-de-3-a6e48fb5e1d3](https://medium.com/mandabugs/mysql-tipos-de-dados-introdu%C3%A7%C3%A3o-e-dados-num%C3%A9ricos-1-de-3-a6e48fb5e1d3). Acesso em 06 Abr. 2023.
* MySQL Data Types: [https://dev.mysql.com/doc/refman/8.0/en/data-types.html](https://dev.mysql.com/doc/refman/8.0/en/data-types.html)
* [https://dev.mysql.com/doc/refman/8.0/en/fixed-point-types.html](https://dev.mysql.com/doc/refman/8.0/en/fixed-point-types.html)
* [https://www.w3schools.com/mysql/mysql\_datatypes.asp](https://www.w3schools.com/mysql/mysql\_datatypes.asp)

[^1]: um oferecimento "Wanessa Traduz"
