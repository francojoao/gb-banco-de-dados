---
description: >-
  A etapa inicial do projeto de banco de dados é a análise de requisitos de um
  dado cenário. Precisamos analisar com cautela o que se pede, uma vez que cada
  mini-mundo tem suas próprias especificidades.
---

# 🗣 Análise de Requisitos

Imagine que precisamos desenvolver um sistema para informatização de uma escola de ensino médio. Neste sistema, sabe-se que são registrados os dados de estudantes matriculados, de professores que lecionam na instituição e das disciplinas. Um dos objetivos é digitalizar os diários de classe. Para atingir os objetivos do sistema, é necessário utilizar um [sistema de banco de dados](#user-content-fn-1)[^1], cuja descrição do mini-mundo[^2] é apresentada abaixo.

{% hint style="success" %}
#### **Descrição do mini-mundo Escola**

* **Estudantes** cursam disciplinas, que são lecionadas por um docente cada uma. Para cada estudante deve-se manter o nome, a idade, os telefones para contato, o endereço completo, e as informações de matrícula.&#x20;
* Uma **disciplina** é cursada por vários estudantes e é lecionada por um docente. Das disciplinas, deseja-se saber o nome, a descrição, o código e a carga horária.
* **Docentes** lecionam diversas disciplinas cada um e em cada disciplina possui diversos estudantes. De cada docente, deseja-se saber o nome, o código de matrícula, o e-mail institucional e o telefone.
{% endhint %}

[^1]: 

[^2]: 
