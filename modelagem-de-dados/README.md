---
description: >-
  Esta página descreve os principais elementos e as características do modelo
  entidade-relacionamento (ER), técnica de modelagem conceitual de dados.
cover: >-
  https://images.unsplash.com/photo-1544383835-bda2bc66a55d?crop=entropy&cs=tinysrgb&fm=jpg&ixid=MnwxOTcwMjR8MHwxfHNlYXJjaHwxfHxkYXRhYmFzZXxlbnwwfHx8fDE2Nzk0OTQ5NDM&ixlib=rb-4.0.3&q=80
coverY: 0
layout: landing
---

# ✈ Modelo Entidade-Relacionamento

Imagine que precisamos desenvolver um sistema para informatização de uma escola de ensino médio. Neste sistema, sabe-se que são registrados os dados de estudantes matriculados, de professores que lecionam na instituição e das disciplinas. Um dos objetivos é digitalizar os diários de classe. Para atingir os objetivos do sistema, é necessário utilizar um [sistema de banco de dados](#user-content-fn-1)[^1], cuja descrição do mini-mundo[^2] é apresentada abaixo.

{% hint style="success" %}
#### **Descrição do mini-mundo Escola**

* **Estudantes** cursam disciplinas, que são lecionadas por um docente cada uma. Para cada estudante deve-se manter o nome, a idade, os telefones para contato, o endereço completo, e as informações de matrícula.&#x20;
* Uma **disciplina** é cursada por vários estudantes e é lecionada por um docente. Das disciplinas, deseja-se saber o nome, a descrição, o código e a carga horária.
* **Docentes** lecionam diversas disciplinas cada um e em cada disciplina possui diversos estudantes. De cada docente, deseja-se saber o nome, o código de matrícula, o e-mail institucional e o telefone.
{% endhint %}

A modelagem é uma das etapas necessárias para a concepção do banco de dados de nossa aplicação; a técnica entidade-relacionamento é uma das mais populares para o projeto de banco de dados.&#x20;

> A técnica _entidade-relacionamento_ (ER) para a modelagem de dados conceitual (...) foi apresentada inicialmente em 1976 por Peter Chen. O formato Chen do modelo ER emprega retângulos para especificar entidades, que de certa forma são semelhantes a registros. Ele também usa objetos em forma de losango para representar os vários tipos de relacionamentos, que são diferenciados por números ou letras colocadas nas linhas que conectam os losangos aos retângulos.
>
> 💬 (TEOREY et al., 2013, p. 9)

## Caracterização do modelo entidade-relacionamento

As tarefas fundamentais da modelagem conceitual baseada na abordagem ER, segundo Teorey et al. (2013, p. 58), são:&#x20;

* a classificação das entidades e seus respectivos atributos;
* a especificação dos relacionamentos;
* e a determinação das hierarquias de generalização.

## Elementos do modelo entidade-relacionamento

<table data-view="cards"><thead><tr><th></th><th></th><th></th></tr></thead><tbody><tr><td><strong>Entidades</strong></td><td>Representações de elementos concretos ou abstratos do "mundo real"</td><td></td></tr><tr><td><strong>Relacionamentos</strong></td><td>Associações entre duas ou mais entidades representadas.</td><td></td></tr><tr><td><strong>Atributos</strong></td><td>Propriedades/ características de uma entidade/relacionamento</td><td></td></tr></tbody></table>



## Referências

* TEOREY, T. J. et al. **Projeto e Modelagem de Banco de Dados**: Tradução da 5ª Edição. \[S.l.]: Elsevier, 2013. v. 1.
* SILBERSCHATZ, A.; KORTH, H. F.; SUDARSHAN, S. **Sistemas de Banco de Dados**. 3. ed. São Paulo: Pearson Makron Books, 1999.
* HEUSER, C. A. **Projeto de banco de dados**: Volume 4 da Série Livros did́áticos informática UFRGS. \[S.l.]: Bookman Editora, 2009.
* HENRIQUE NETO, G. **Modelagem de banco de dados**. Rio de Janeiro: Editora SESES, 2015.
* ELMASRI, R.; NAVATHE, S. B. **Sistemas de banco de dados**. 6. ed. São Paulo: Pearson Addison Wesley, 2011.

[^1]: 

[^2]: 
