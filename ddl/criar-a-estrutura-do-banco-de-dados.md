---
description: >-
  Concluído o processo de modelagem de dados, partimos para a construção do
  banco de dados. Como estamos trabalhando com um BD relacional, utilizaremos os
  comandos SQL descritos nesta página para isso.
---

# 🧱 Criar a estrutura do banco de dados

## Step 1. Criar o esquema do banco de dados

{% code title="O comando CREATE DATABASE" lineNumbers="true" %}
```sql
CREATE DATABASE Escola;
```
{% endcode %}

## Step 2. Criar uma tabela

{% code title="O comando CREATE TABLE" lineNumbers="true" %}
```sql
CREATE TABLE Estudante(
    idEstudante INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(60) NOT NULL,
    nascimento DATE NOT NULL,
    matricula CHAR(12) NOT NULL
);
```
{% endcode %}

## Step 3. Inserir dados em uma tabela criada

{% code title="O comando INSERT INTO" lineNumbers="true" %}
```sql
INSERT INTO Estudante
VALUES
    (1, 'Harry James Potter',    '1980-07-31', '1991.001.007'),
    (2, 'Ronald Bilius Weasley', '1980-03-01', '1991.001.016'),
    (3, 'Hermione Jean Granger', '1979-09-19', '1991.001.001')
```
{% endcode %}

## Step 4. Consultar os dados de uma tabela criada

{% code title="O comando SELECT" lineNumbers="true" %}
```sql
SELECT * FROM Estudante;
```
{% endcode %}



## Referências

*
