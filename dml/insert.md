---
description: Inserir dados é um função crucial para a construção do Banco de Dados.
---

# 📝 INSERT

Para usar o comando **`INSERT INTO`**, devemos informar uma tabela do banco de dados e as colunas que receberão novos valores. E junto com a palavra chave **VALUES**, você informará o conjunto de dados que serão inserido.

{% code title="Exemplo" overflow="wrap" lineNumbers="true" fullWidth="true" %}
```sql
-- INSERT INTO
INSERT INTO Estudante (idEstudante, nome, nascimento, matricula)
VALUES (1001, 'Miguel Brandão', '2007-05-12', '2023.124.204');
```
{% endcode %}

No trecho de código acima, temos o exemplo de uso do comando INSERT INTO:

* Na linha 2, temos a indicação do comando `INSERT INTO` e o nome da tabela onde os dados serão inseridos: <mark style="color:blue;">Estudante</mark>;
* Já na linha 3, temos os valores a serem inseridos, indicados após a palavra reservada `VALUES`: <mark style="color:blue;">idEstudante</mark>, <mark style="color:blue;">nome</mark>, <mark style="color:blue;">nascimento</mark>, <mark style="color:blue;">matricula</mark>.



## Inserir múltiplos dados em um único `INSERT INTO`

Podemos inserir os dados de vários estudantes além de Miguel Brandão. Para isto, precisamos acrescentar uma vírgula depois do [parêntese que fecha](#user-content-fn-1)[^1] o primeiro registro:

{% code title="" overflow="wrap" lineNumbers="true" fullWidth="true" %}
```sql
-- INSERT INTO
INSERT INTO 
    Estudante (idEstudante, nome, nascimento, matricula)
VALUES 
    (1001, 'Miguel Brandão', '2007-05-12', '2023.124.204'),
    (1002, 'Carlos Feitosa', '2007-12-21', '2023.123.204'),
    (1003, 'Gregório Silva', '2007-09-03', '2023.123.204'),
    (1004, 'Marina Pereira', '2007-04-07', '2023.123.204'),
    (1005, 'Glória Tavares', '2007-06-15', '2023.123.204');
```
{% endcode %}



As informações serão inseridas

\-- Ordem dos atributos, `NULL` / `NOT NULL`, `UNIQUE`, `Foreign Key`



## O comando INSERT IGNORE

INSERT IGNORE (?), ON DUPLICATE KEYS (?)

##

## Referências

* Oracle. **13.2.7 INSERT Statement**. Disponível em: [https://dev.mysql.com/doc/refman/8.0/en/insert.html](https://dev.mysql.com/doc/refman/8.0/en/insert.html). Acesso em: 17 Set. 2023.



[^1]: )
