---
description: >-
  Com as entidades, os relacionamentos e os respectivos atributos definidos,
  passaremos aos refinamentos do nosso diagrama, aplicando as classificações de
  atributos definidas por diferentes autores.
layout: landing
---

# 🧠 Tipos de atributos

<img src="../../../.gitbook/assets/file.excalidraw (17).svg" alt="" class="gitbook-drawing">



## Classificação dos atributos quanto ao valor

A partir da descrição do mini-mundo, percebe-se que o atributo telefones, da entidade Estudante, é descrito no plural. Por conseguinte, entende-se que um estudante pode ter cadastrado vários telefones para contato - logo, pode apresentar diferentes valores. Este é um tipo particular de atributo, chamado de <mark style="color:purple;">**atributo multivalorado**</mark>.&#x20;

<img src="../../../.gitbook/assets/file.excalidraw (23).svg" alt="" class="gitbook-drawing">

Outros atributos, como o nome (valor único, uma pessoa só pode ter um nome) e a matrícula, são únicos, afinal, uma pessoa só pode ter um nome e a matrícula do estudante é um valor único e individual. Neste caso, temos exemplos de <mark style="color:purple;">**atributos monovalorados**</mark>.

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th><th></th></tr></thead><tbody><tr><td><mark style="color:purple;"><strong>Atributo monovalorado/único</strong></mark></td><td>atributos que, para uma ocorrência de entidade, só podem assumir um único valor (ELMASRI; NAVATHE, 2011).</td><td><p></p><p><strong>Exemplos:</strong></p><p><code>Docente</code>: nome, matricula</p><p><code>Disciplina</code>: descricao, codigo, creditos</p><p><code>Estudante</code>: nome, matricula</p></td></tr><tr><td><mark style="color:purple;"><strong>Atributo multivalorado</strong></mark></td><td><p>para uma ocorrência de entidade, podem assumir mais de um valor</p><p>(SILBERSCHATZ; KORTH; SUDARSHAN, 1999).</p></td><td><p><strong>Exemplos:</strong></p><p><code>Docente</code>: telefones</p><p><code>Estudante</code>: emails, telefones</p></td></tr></tbody></table>



## Classificação dos atributos a partir das subdivisões

Ao realizar a matrícula de um estudante, armazena-se, entre outros atributos, o endereço. Sabe-se que um endereço apresenta um conjunto de dados: logradouro, número da residência, nome do bairro, CEP, cidade, etc. Assim, podemos nos referir ao endereço como um <mark style="color:green;">**atributo composto**</mark>.

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th><th></th></tr></thead><tbody><tr><td><mark style="color:green;"><strong>Atributo simples/atômico</strong></mark></td><td>não podem ser repartidos, isto é, encerram-se em si próprios</td><td><p></p><p><strong>Exemplo:</strong></p><p><code>Estudante</code>: nome, idade</p></td></tr><tr><td><mark style="color:green;"><strong>Atributo composto</strong></mark></td><td>formados por partes que correspondem a fragmentos menores sobre o mesmo elemento (HENRIQUE NETO, 2015, p. 64).</td><td><p><strong>Exemplo:</strong></p><p><code>Estudante</code>: atributo endereço composto por logradouro, número, bairro e CEP.</p></td></tr></tbody></table>

O valor de um atributo composto é “a concatenação dos valores de seus componentes atributos simples” (ELMASRI; NAVATHE, 2011, p. 135).

Atributos compostos são indicados em situações em que é possível fazer referência “ao atributo como um todo em determinadas ocasiões e somente a parte dele em outras” (SILBERSCHATZ; KORTH; SUDARSHAN, 1999, p. 23).

<img src="../../../.gitbook/assets/file.excalidraw (15).svg" alt="" class="gitbook-drawing">

Além disso, o atributo composto pode compor uma escala hierárquica, onde as partes que o compõem são semanticamente autônomas (ELMASRI; NAVATHE, 2011, p. 135), isto é, têm sentido próprio por si próprias.  Um exemplo disso é o próprio atributo endereço, da entidade `Estudante`: ora é possível fazer referência ao endereço como um todo, ora pode ser necessário saber apenas o bairro ou CEP.&#x20;



## Classificação dos atributos quanto ao armazenamento

<img src="../../../.gitbook/assets/file.excalidraw (19).svg" alt="" class="gitbook-drawing">

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th><th></th></tr></thead><tbody><tr><td><mark style="color:orange;"><strong>Atributo armazenado</strong></mark></td><td>o dado pode ser armazenado diretamente e não é originário de nenhum tratamento computacional; </td><td><p></p><p></p><p><strong>Exemplo:</strong></p><p><code>Estudante</code>: data de nascimento</p></td></tr><tr><td><mark style="color:orange;"><strong>Atributo derivado</strong></mark></td><td>decorre de outro atributo ou entidade (SILBERSCHATZ; KORTH; SUDARSHAN, 1999, p. 24), sendo obtido a partir “de um processamento específico” (HENRIQUE NETO, 2015, p. 65)</td><td><p><strong>Exemplo:</strong></p><p><code>Estudante</code>: idade</p></td></tr></tbody></table>



## Diagrama finalizado (so far...)

<img src="../../../.gitbook/assets/file.excalidraw (10).svg" alt="" class="gitbook-drawing">



## Referências

* ELMASRI, R.; NAVATHE, S. B. **Sistemas de banco de dados**. 6. ed. São Paulo: Pearson Addison Wesley, 2011.
* HENRIQUE NETO, G. **Modelagem de banco de dados**. Rio de Janeiro: Editora SESES, 2015.
* HEUSER, C. A. **Projeto de banco de dados**: Volume 4 da Série Livros did́áticos informática UFRGS. \[S.l.]: Bookman Editora, 2009.
* SILBERSCHATZ, A.; KORTH, H. F.; SUDARSHAN, S. **Sistemas de Banco de Dados**. 3. ed. São Paulo: Pearson Makron Books, 1999.
* TEOREY, T. J. et al. **Projeto e Modelagem de Banco de Dados**: Tradução da 5ª Edição. \[S.l.]: Elsevier, 2013. v. 1.
