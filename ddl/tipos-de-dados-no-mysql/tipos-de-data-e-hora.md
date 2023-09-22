---
description: >-
  Eventualmente, pode ser necessário armazenar dados que fazem referência a data
  e hora no banco de dados. Para isso, o MySQL oferece algumas possibilidades,
  resumidamente descritas nesta página.
layout: editorial
---

# 📆 Tipos de data e hora

A documentação do MySQL indica que existe um conjunto de valores válidos para os tipos relacionados a data e hora, e também um valor "zero" para os casos em que pode ser necessário especificar um valor que não pode ser representado. Os tipos temporais são listados na tabela abaixo.

| Tipo                                         | Formato padrão        | Valores permitidos                                                 |
| -------------------------------------------- | --------------------- | ------------------------------------------------------------------ |
| <mark style="color:blue;">`YEAR`</mark>      | 'YYYY'                | <p>0000, </p><p>1901 a 2155</p>                                    |
| <mark style="color:blue;">`DATE`</mark>      | 'YYYY-MM-DD'          | <p>'1000-01-01' a </p><p>'9999-12-31'</p>                          |
| <mark style="color:blue;">`TIME`</mark>      | 'hh:mm:ss'            | <p>'-838:59:59' a</p><p>'838:59:59'</p>                            |
| <mark style="color:blue;">`DATETIME`</mark>  | 'YYYY-MM-DD hh:mm:ss' | <p>'1000-01-01 00:00:00' a </p><p>'9999-12-31 23:59:59'</p>        |
| <mark style="color:blue;">`TIMESTAMP`</mark> | 'YYYY-MM-DD hh:mm:ss' | <p>'1970-01-01 00:00:01' UTC a</p><p>'2038-01-09 03:14:07' UTC</p> |

<img src="../../.gitbook/assets/file.excalidraw (5) (1).svg" alt="" class="gitbook-drawing">

## Inicialização e atualização de data e hora

Para os tipos <mark style="color:blue;">`TIMESTAMP`</mark> e <mark style="color:blue;">`DATETIME`</mark>, a documentação do MySQL indica que é possível associar o "carimbo" de data e hora atuais como valor padrão, auto-atualizado ou ambos, para linhas inseridas que não especificam um valor para a coluna ou atualizadas para o valor atual quando o valor de qualquer outra coluna na linha é alterado para o valor atual.&#x20;

Assim, define-se a inicialização e atualização automática para data e hora atual na estruturação das colunas de uma tabela, a partir do <mark style="color:blue;">`DEFAULT CURRENT_TIMESTAMP`</mark> e <mark style="color:blue;">`ON UPDATE CURRENT_TIMESTAMP`</mark>.

## Referências

* [https://dev.mysql.com/doc/refman/8.0/en/timestamp-initialization.html](https://dev.mysql.com/doc/refman/8.0/en/timestamp-initialization.html)
* [https://dev.mysql.com/doc/refman/8.0/en/time.html](https://dev.mysql.com/doc/refman/8.0/en/time.html)
* [https://dev.mysql.com/doc/refman/8.0/en/date-and-time-types.html](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-types.html)
* [https://medium.com/mandabugs/mysql-tipos-de-dados-data-hora-2-de-3-c147a8d90f93](https://medium.com/mandabugs/mysql-tipos-de-dados-data-hora-2-de-3-c147a8d90f93)
