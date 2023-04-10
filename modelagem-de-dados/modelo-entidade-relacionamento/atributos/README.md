---
description: >-
  Entidades e relacionamentos têm um conjunto de características que os
  descrevem. No modelo entidade-relacionamento (MER), esse elemento é chamado de
  atributo, nosso objeto de estudo nesta página.
layout: landing
---

# 💪 Atributos

{% hint style="success" %}
**Descrição do do mini-mundo**

* **Estudantes** cursam disciplinas, que são lecionadas por um docente cada uma. Para cada estudante deve-se manter o nome, a idade, os telefones para contato, o endereço completo (incluindo logradouro, número, bairro e CEP), e as informações de matrícula.&#x20;
* Uma **disciplina** é cursada por vários estudantes e é lecionada por um docente. Das disciplinas, deseja-se saber código, número de créditos e descrição.
* **Docentes** lecionam diversas disciplinas cada um e em cada disciplina possui diversos estudantes. De cada docente, deseja-se saber o nome, o código de matrícula, o e-mail institucional e o telefone.
{% endhint %}

Na descrição do mini-mundo, observamos que as entidades apresentam um conjunto de dados que caracterizam cada instância dessas entidades. Esses dados são chamados de **propriedades** ou **atributos,** que possuem respectivos valores que a caracterizam em cada ocorrência específica (TEOREY et al., 2013, p. 18).

No caso da entidade `Estudante`, por exemplo, observamos que todo estudante tem: nome, telefones para contato, endereço, informações de matrícula e idade. Cada campo assume valores específicos, como ilustra a tabela abaixo.

<table><thead><tr><th>nome</th><th>telefones</th><th>endereço</th><th>matrícula</th><th data-type="number">idade</th><th data-hidden data-type="users" data-multiple></th></tr></thead><tbody><tr><td>Ana Maria de Souza Marques</td><td>71912345678, 77912348765</td><td>Alameda dos Anjos, 7, Bairro da Paz, 12345-67</td><td>2023001</td><td>15</td><td></td></tr><tr><td>Paulo Matias de Almeida Santos</td><td>77987654321</td><td>Avenida Maria Felipa, 89, Guerreira Zeferina, 12345-60</td><td>2023002</td><td>14</td><td></td></tr><tr><td>Carlos Eduardo Moura Castro</td><td>77932659874</td><td>Rua da Bahia, 13, Guerreira Zeferina, 12345-68</td><td>2023003</td><td>16</td><td></td></tr><tr><td>Bianca Souto Correia</td><td>77974185296</td><td>Ladeira Joana Angélica, 1, Centro, 12345-01</td><td>2023004</td><td>15</td><td></td></tr><tr><td>Maria Marta do Amor Divino</td><td>77912457836</td><td>1ª Travessa Maria Felipa, 6, Guerreira Zeferina, 12345-60 </td><td>2023005</td><td>14</td><td></td></tr><tr><td>Hércules da Silva Caires</td><td>77988653214, 77903265948</td><td>Praça Gal Costa, s/n, Glória, 12345-59</td><td>2023006</td><td>15</td><td></td></tr><tr><td>Carlos Eduardo Pinto Tavares</td><td>77901254789</td><td>Rua da Bahia, 13, Guerreira Zeferina, 12345-68</td><td>2023007</td><td>16</td><td></td></tr></tbody></table>

{% hint style="info" %}
Quando necessário, para evitar que a leitura do diagrama ER seja prejudicada, os atributos são omitidos e adota-se uma representação textual separada do diagrama (HEUSER, 2009, p. 48).
{% endhint %}

Os diferentes autores apresentam algumas classificações para os atributos, de acordo com critérios específicos, cuja compreensão é necessária para a elaboração do diagrama ER e, na maioria dos casos, na transposição para o modelo relacional. Esses tipos de atributos são abordados na página [Tipos de atributos](tipos-de-atributos.md).



## Step 4. Identificar os atributos

<img src="../../../.gitbook/assets/file.excalidraw (31).svg" alt="" class="gitbook-drawing">

É possível, ainda, classificar os atributos de acordo com diversos critérios. Diferentes autores apresentam alguns tipos de atributos, cuja compreensão é relevante no processo de conversão da modelagem conceitual ER para o modelo lógico relacional.&#x20;

### Classificação quanto à função

Uma primeira classificação é decorrente da função que exerce aquele atributo dentro do banco. Se o atributo pode ser usado para apontar uma ocorrência de entidade específica (TEOREY et al., 2013, p. 18), trata-se de um <mark style="color:yellow;">**atributo chave**</mark>.&#x20;

* <mark style="color:yellow;background-color:yellow;">**Atributo chave**</mark>: também referido como atributo identificador/restrição de exclusividade, um atributo chave é usado para diferenciar entidades de forma específica (ELMASRI; NAVATHE, 2011, p. 137); estabelece relações e distingue as múltiplas linhas/tuplas de uma tabela/relação (HEUSER, 2009, p. 122);&#x20;

<img src="../../../.gitbook/assets/file.excalidraw (35).svg" alt="Inseridos os atributos chaves de cada entidade." class="gitbook-drawing">

* <mark style="color:yellow;background-color:yellow;">**Atributo descritor**</mark>**:** quando o atributo _apenas_ ~~(como se fosse pouca coisa)~~ descreve alguma característica da entidade a que pertence. Caso dos demais atributos das três entidades, definidos previamente.

Na página seguinte, tratamos de outras classificações de atributos importantes para o refinamento do diagrama e, principalmente, do banco de dados que este diagrama representa.



## Referências

* ELMASRI, R.; NAVATHE, S. B. **Sistemas de banco de dados**. 6. ed. São Paulo: Pearson Addison Wesley, 2011.
* HENRIQUE NETO, G. **Modelagem de banco de dados**. Rio de Janeiro: Editora SESES, 2015.
* HEUSER, C. A. **Projeto de banco de dados**: Volume 4 da Série Livros did́áticos informática UFRGS. \[S.l.]: Bookman Editora, 2009.
* SILBERSCHATZ, A.; KORTH, H. F.; SUDARSHAN, S. **Sistemas de Banco de Dados**. 3. ed. São Paulo: Pearson Makron Books, 1999.
* TEOREY, T. J. et al. **Projeto e Modelagem de Banco de Dados**: Tradução da 5ª Edição. \[S.l.]: Elsevier, 2013. v. 1.
