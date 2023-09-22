---
description: >-
  Às vezes é necessário modificar uma tabela existente em um banco de dados.
  Para isso, contamos com o comando ALTER TABLE.
---

# 🪚 Alterar tabelas

## Adicionar e excluir colunas

Podemos utilizar o `ALTER TABLE` para adicionar ou excluir uma coluna de uma tabela existente. Isso é útil quando precisamos aumentar a estrutura da tabela para incluir novos dados ou reduzir os dados já existentes.

### ADD COLUMN



<img src="../.gitbook/assets/file.excalidraw.svg" alt="" class="gitbook-drawing">

<pre class="language-sql" data-title="Exemplo"><code class="lang-sql"><strong>ALTER TABLE Estudante
</strong>ADD COLUMN sobrenome VARCHAR(50) NOT NULL;
</code></pre>

### DROP COLUMN



<img src="../.gitbook/assets/file.excalidraw (1).svg" alt="" class="gitbook-drawing">

{% code title="ALTER TABLE/DROP COLUMN" %}
```sql
ALTER TABLE Estudante
DROP COLUMN sobrenome;
```
{% endcode %}

##

## Renomear uma tabela (ALTER TABLE/RENAME TO)

<img src="../.gitbook/assets/file.excalidraw (2).svg" alt="" class="gitbook-drawing">

{% code title="ALTER TABLE/RENAME TO" %}
```sql
ALTER TABLE Estudante
RENAME TO Aluno;
```
{% endcode %}

##

## Renomear, redefinir e reordenar colunas



### CHANGE

<img src="../.gitbook/assets/file.excalidraw (3).svg" alt="" class="gitbook-drawing">



### MODIFY

<img src="../.gitbook/assets/file.excalidraw (4).svg" alt="" class="gitbook-drawing">



## Chaves

### Chaves primárias

<img src="../.gitbook/assets/file.excalidraw (23).svg" alt="" class="gitbook-drawing">

{% code fullWidth="true" %}
```sql
ALTER TABLE nome_da_tabela
ADD PRIMARY KEY (nome_da_coluna);
```
{% endcode %}

### Chaves estrangeiras

<img src="../.gitbook/assets/file.excalidraw (22).svg" alt="" class="gitbook-drawing">

{% code fullWidth="true" %}
```sql
ALTER TABLE nome_da_tabela
ADD PRIMARY KEY (nome_da_coluna);
```
{% endcode %}

## Outras restrições

##

## Referências

* MySQL. Alter table. Disponível em: [https://dev.mysql.com/doc/refman/8.0/en/alter-table.html](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html). Acesso em 15 Mar. 2023.
