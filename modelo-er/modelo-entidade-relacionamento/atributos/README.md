# 💪 Atributos

{% hint style="success" %}
**Descrição do do mini-mundo**

* **Estudantes** cursam disciplinas, que são lecionadas por um docente cada uma. Para cada estudante deve-se manter o nome, a idade, os telefones para contato, o endereço completo (incluindo logradouro, número, bairro e CEP), e as informações de matrícula.&#x20;
* Uma **disciplina** é cursada por vários estudantes e é lecionada por um docente. Das disciplinas, deseja-se saber código, número de créditos e descrição.
* **Docentes** lecionam diversas disciplinas cada um e em cada disciplina possui diversos estudantes. De cada docente, deseja-se saber o nome, o código de matrícula, o e-mail institucional e o telefone.
{% endhint %}

## Step by step

### Step 1. Identificar as entidades

Como combinamos, neste primeiro passo, identificaremos as entidades apresentadas na descrição do mini-mundo. De imediato, é possível notar que estudantes, professores e disciplinas apresentam características próprias.

<img src="../../../.gitbook/assets/file.excalidraw (6).svg" alt="" class="gitbook-drawing">

### Step 2. Identificar os atributos

<img src="../../../.gitbook/assets/file.excalidraw (7).svg" alt="" class="gitbook-drawing">

### Step 3. Identificar os relacionamentos

Logo no início da descrição do mini-mundo, observa-se que existe uma associação entre as entidades **`Estudante`** e **`Docente`** com a entidade **`Disciplina`**.

> **Estudantes** cursam disciplinas, que são lecionadas por um docente cada uma.

<img src="../../../.gitbook/assets/file.excalidraw (3) (1).svg" alt="" class="gitbook-drawing">

A partir dessa leitura, analisamos: existe associação entre **`Docente`** e **`Estudante`**? Se as disciplinas cursadas pelos discentes são lecionadas por professores, supõe-se que há alguma associação entre estas entidades. Vamos partir para a análise das cardinalidades dos relacionamentos e das restrições de participação antes de alterar o diagrama.

### Step 4. Definir as cardinalidades dos relacionamentos

Conforme a descrição do mini-mundo, "**Estudantes** cursam disciplinas" e "Uma **disciplina** é cursada por vários estudantes". Percebe-se que o estudante cursa, no mínimo, uma disciplina, e pode cursar mais de uma ao mesmo tempo; assim, a cardinalidade mínima é 1 e a cardinalidade máxima é N.

{% hint style="warning" %}
Não esqueça: marcamos as cardinalidades **do lado oposto** (sentido da seta em <mark style="color:blue;background-color:blue;">**azul**</mark> nas figuras abaixo).
{% endhint %}

<img src="../../../.gitbook/assets/file.excalidraw (4).svg" alt="" class="gitbook-drawing">

Nessa imagem abaixo, expressamos a associação entre disciplina e estudante: no mínimo, uma disciplina pode ser cursada por _nenhum_ estudante (cardinalidade mínima _0_) e, no máximo, _vários_ estudantes (cardinalidade máxima _N_).

<img src="../../../.gitbook/assets/file.excalidraw (5).svg" alt="" class="gitbook-drawing">

Assim, as cardinalidades ficam conforme a figura a seguir:

<img src="../../../.gitbook/assets/file.excalidraw (1).svg" alt="" class="gitbook-drawing">

### Step 5. Refinar o modelo

#### Classificando os atributos a partir dos valores possíveis

A partir da descrição do mini-mundo, percebe-se que o atributo telefones, da entidade Estudante, é descrito no plural. Por conseguinte, entende-se que um estudante pode ter cadastrado vários telefones para contato - logo, pode apresentar diferentes valores. Este é um tipo particular de atributo, chamado de <mark style="color:purple;">**atributo multivalorado**</mark>.&#x20;

Outros atributos, como o nome (valor único, uma pessoa só pode ter um nome) e a matrícula, são únicos, afinal, uma pessoa só pode ter um nome e a matrícula do estudante é um valor único e individual. Neste caso, temos exemplos de <mark style="color:purple;">**atributos monovalorados**</mark>.

<img src="../../../.gitbook/assets/file.excalidraw (8).svg" alt="Na entidade Estudante, telefone e emails são exemplos de atributos multivalorados." class="gitbook-drawing">

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th><th></th></tr></thead><tbody><tr><td><mark style="color:purple;"><strong>Atributo monovalorado</strong></mark></td><td>atributos que, para uma ocorrência de entidade, só podem assumir um único valor (ELMASRI; NAVATHE, 2011).</td><td><p><strong></strong></p><p><strong>Exemplos:</strong></p><p><code>Docente</code>: nome, matricula</p><p><code>Disciplina</code>: descricao, codigo, creditos</p><p><code>Estudante</code>: nome, matricula</p></td></tr><tr><td><mark style="color:purple;"><strong>Atributo multivalorado</strong></mark></td><td><p>para uma ocorrência de entidade, podem assumir mais de um valor</p><p>(SILBERSCHATZ; KORTH; SUDARSHAN, 1999).</p></td><td><p><strong>Exemplos:</strong></p><p><code>Docente</code>: telefones</p><p><code>Estudante</code>: emails, telefones</p></td></tr></tbody></table>

#### Classificação dos atributos a partir das subdivisões

<img src="../../../.gitbook/assets/file.excalidraw (2).svg" alt="" class="gitbook-drawing">

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th><th></th></tr></thead><tbody><tr><td><mark style="color:green;"><strong>Atributo simples/atômico</strong></mark></td><td>não podem ser repartidos, isto é, encerram-se em si próprios</td><td></td></tr><tr><td><mark style="color:green;"><strong>Atributo composto</strong></mark></td><td>formados por partes que correspondem a fragmentos menores sobre o mesmo elemento (HENRIQUE NETO, 2015, p. 64)</td><td></td></tr></tbody></table>

#### Classificações quanto ao armazenamento

<img src="../../../.gitbook/assets/file.excalidraw (3).svg" alt="" class="gitbook-drawing">

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th><th></th></tr></thead><tbody><tr><td><mark style="color:orange;"><strong>Atributo armazenado</strong></mark></td><td>o dado pode ser armazenado diretamente e não é originário de nenhum tratamento computacional; </td><td><p><strong>Exemplo:</strong></p><p><code>Estudante</code>: data de nascimento</p></td></tr><tr><td><mark style="color:orange;"><strong>Atributo derivado</strong></mark></td><td>decorre de outro atributo ou entidade (SILBERSCHATZ; KORTH; SUDARSHAN, 1999, p. 24), sendo obtido a partir “de um processamento específico” (HENRIQUE NETO, 2015, p. 65)</td><td><p><strong>Exemplo:</strong></p><p><code>Estudante</code>: idade</p></td></tr></tbody></table>

### Diagrama concluído

<img src="../../../.gitbook/assets/file.excalidraw.svg" alt="" class="gitbook-drawing">

## Referências

* ELMASRI, R.; NAVATHE, S. B. **Sistemas de banco de dados**. 6. ed. São Paulo: Pearson Addison Wesley, 2011.
* HENRIQUE NETO, G. **Modelagem de banco de dados**. Rio de Janeiro: Editora SESES, 2015.
* HEUSER, C. A. **Projeto de banco de dados**: Volume 4 da Série Livros did́áticos informática UFRGS. \[S.l.]: Bookman Editora, 2009.
* SILBERSCHATZ, A.; KORTH, H. F.; SUDARSHAN, S. **Sistemas de Banco de Dados**. 3. ed. São Paulo: Pearson Makron Books, 1999.
* TEOREY, T. J. et al. **Projeto e Modelagem de Banco de Dados**: Tradução da 5ª Edição. \[S.l.]: Elsevier, 2013. v. 1.
