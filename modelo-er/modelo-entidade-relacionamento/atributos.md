# 💪 Atributos

{% hint style="success" %}
**Descrição do do mini-mundo**

* **Estudantes** cursam disciplinas, que são lecionadas por um docente cada uma. Para cada estudante deve-se manter o nome, os telefones para contato e as informações de matrícula.&#x20;
* Uma **disciplina** é cursada por vários estudantes e é lecionada por um docente. Das disciplinas, deseja-se saber código, número de créditos e descrição.
* **Docentes** lecionam diversas disciplinas cada um e em cada disciplina possui diversos estudantes. De cada docente, deseja-se saber o nome, o código de matrícula, o e-mail institucional e o telefone.
{% endhint %}

## Step by step

### Step 1. Identificar as entidades

Como combinamos, neste primeiro passo, identificaremos as entidades apresentadas na descrição do mini-mundo. De imediato, é possível notar que estudantes, professores e disciplinas apresentam características próprias.

<img src="../../.gitbook/assets/file.excalidraw (1).svg" alt="" class="gitbook-drawing">

### Step 2. Identificar os atributos

<table data-view="cards"><thead><tr><th></th><th></th><th></th></tr></thead><tbody><tr><td><strong>Estudante</strong></td><td><p>nome</p><p>telefones para contato</p><p>informações de matrícula</p></td><td></td></tr><tr><td><strong>Docente</strong></td><td><p>nome</p><p>código de matrícula</p><p>e-mail institucional</p><p>telefone</p></td><td></td></tr><tr><td><strong>Disciplina</strong></td><td><p>código</p><p>número de créditos descrição</p></td><td></td></tr></tbody></table>

### Step 3. Identificar os relacionamentos

Logo no início da descrição do mini-mundo, observa-se que existe uma associação entre as entidades **`Estudante`** e **`Docente`** com a entidade **`Disciplina`**.

> **Estudantes** cursam disciplinas, que são lecionadas por um docente cada uma.

<img src="../../.gitbook/assets/file.excalidraw (3).svg" alt="" class="gitbook-drawing">

A partir dessa leitura, analisamos: existe associação entre **`Docente`** e **`Estudante`**? Se as disciplinas cursadas pelos discentes são lecionadas por professores, supõe-se que há alguma associação entre estas entidades. Vamos partir para a análise das cardinalidades dos relacionamentos e das restrições de participação antes de alterar o diagrama.

### Step 4. Definir as cardinalidades dos relacionamentos

Conforme a descrição do mini-mundo, "**Estudantes** cursam disciplinas" e "Uma **disciplina** é cursada por vários estudantes". Percebe-se que o estudante cursa, no mínimo, uma disciplina, e pode cursar mais de uma ao mesmo tempo; assim, a cardinalidade mínima é 1 e a cardinalidade máxima é N.

{% hint style="warning" %}
Não esqueça: marcamos as cardinalidades **do lado oposto** (sentido da seta em <mark style="color:blue;background-color:blue;">**azul**</mark> nas figuras abaixo).
{% endhint %}

<img src="../../.gitbook/assets/file.excalidraw (4).svg" alt="" class="gitbook-drawing">

Nessa imagem abaixo, expressamos a associação entre disciplina e estudante: no mínimo, uma disciplina pode ser cursada por _nenhum_ estudante (cardinalidade mínima _0_) e, no máximo, _vários_ estudantes (cardinalidade máxima _N_).

<img src="../../.gitbook/assets/file.excalidraw (5).svg" alt="" class="gitbook-drawing">

Assim, as cardinalidades ficam conforme a figura a seguir:

<img src="../../.gitbook/assets/file.excalidraw.svg" alt="" class="gitbook-drawing">

### Step 5. Refinar o modelo

### Diagrama concluído

<figure><img src="../../.gitbook/assets/Captura de tela de 2023-03-20 13.55.36.png" alt=""><figcaption></figcaption></figure>

## Classificação quanto ao valor&#x20;

* <mark style="color:purple;background-color:purple;">**Atributo único/monovalorado/univalorado**</mark>**:** apresentam “um valor único para uma entidade em particular” (ELMASRI; NAVATHE, 2011, p. 135);
* <mark style="color:purple;background-color:purple;">**Atributo multivalorado**</mark>**:** quando há vários valores para um mesmo atributo de uma mesma instância de entidade (SILBERSCHATZ; KORTH; SUDARSHAN, 1999, p. 23).
* <mark style="color:purple;background-color:purple;">**Em falta/NULL/opcional**</mark>**:** quando “uma entidade em particular pode não ter um valor aplicável para um atributo”, isto é, “quando se sabe que o valor do atributo existe, mas está faltando” (ELMASRI; NAVATHE, 2011, p. 136).

## Classificação quanto às subdivisões

Se o atributo compõe uma escala hierárquica, onde as partes que o compõem são semanticamente autônomas (ELMASRI; NAVATHE, 2011, p. 135).&#x20;

* <mark style="color:green;background-color:green;">**Atributo simples/atômico**</mark>**:** não podem ser repartidos, isto é, encerram-se em si próprios;
* <mark style="color:green;background-color:green;">**Atributo composto**</mark>**:** formados por partes que correspondem a fragmentos menores sobre o mesmo elemento e, portanto, podem ser desmembrados em partes menores associadas a dados (HENRIQUE NETO, 2015, p. 64); assim, podem apresentar uma hierarquia e são “boa escolha quando o usuário deseja se referir ao atributo como um todo em determinadas ocasiões e somente a parte dele em outras” (SILBERSCHATZ; KORTH; SUDARSHAN, 1999, p. 23); o valor desse tipo de atributo é “a concatenação dos valores de seus componentes atributos simples” (ELMASRI; NAVATHE, 2011, p. 135).

## Classificação quanto à função

Se o atributo pode ser usado para apontar uma ocorrência de entidade específica (TEOREY et al., 2013, p. 18).&#x20;

* <mark style="color:yellow;background-color:yellow;">**Identificador/chave/restrição de exclusividade**</mark>**:** usados para diferenciar entidades de forma específica (ELMASRI; NAVATHE, 2011, p. 137); estabelece relações e distingue as múltiplas linhas/tuplas de uma tabela/relação (HEUSER, 2009, p. 122);&#x20;
* <mark style="color:yellow;background-color:yellow;">**Descritor**</mark>**:** quando o atributo apenas descreve alguma característica da entidade a que pertence.

## Classificação quanto ao armazenamento

* <mark style="color:orange;background-color:orange;">**Atributo armazenado/básico/não-derivado**</mark>**:** quando o dado pode ser armazenado diretamente e não é originário de nenhum tratamento computacional;&#x20;
* <mark style="color:orange;background-color:orange;">**Atributo derivado**</mark>**:** ocorre quando o valor do atributo decorre de outro atributo ou entidade (SILBERSCHATZ; KORTH; SUDARSHAN, 1999, p. 24), sendo obtido a partir “de um processamento específico” (HENRIQUE NETO, 2015, p. 65);

<figure><img src="../../.gitbook/assets/flowchart-fun.png" alt=""><figcaption><p>Representação de tipos de atributos apresentados por diferentes autores.</p></figcaption></figure>

## Referências

* ELMASRI, R.; NAVATHE, S. B. **Sistemas de banco de dados**. 6. ed. São Paulo: Pearson Addison Wesley, 2011.
* HENRIQUE NETO, G. **Modelagem de banco de dados**. Rio de Janeiro: Editora SESES, 2015.
* HEUSER, C. A. **Projeto de banco de dados**: Volume 4 da Série Livros did́áticos informática UFRGS. \[S.l.]: Bookman Editora, 2009.
* SILBERSCHATZ, A.; KORTH, H. F.; SUDARSHAN, S. **Sistemas de Banco de Dados**. 3. ed. São Paulo: Pearson Makron Books, 1999.
* TEOREY, T. J. et al. **Projeto e Modelagem de Banco de Dados**: Tradução da 5ª Edição. \[S.l.]: Elsevier, 2013. v. 1.
