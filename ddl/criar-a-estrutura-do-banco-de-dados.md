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
    matricula VARCHAR(12) NOT NULL
);
```
{% endcode %}

## Step 3. Inserir dados em uma tabela criada



## Step 4. Consultar os dados de uma tabela criada





## Referências

*
