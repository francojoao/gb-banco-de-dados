---
description: >-
  Além das entidades, no modelo entidade-relacionamento (MER), outro elemento
  fundamental são as associações entre elas – os relacionamentos –, nosso objeto
  de estudo nesta página.
layout: landing
---

# 🫂 Relacionamentos

Um relacionamento define as associações entre instâncias de entidades (p. 36) que o distinguem de outras instâncias de relacionamentos (HEUSER, 2009, p. 53); a existência de um relacionamento, portanto, é condicionada às entidades sobre as quais representa uma associação (TEOREY et al., 2013, p. 15).

### Step 2. Identificar os relacionamentos

Logo no início da descrição do mini-mundo, observa-se que existe uma associação entre as entidades **`Estudante`** e **`Docente`** com a entidade **`Disciplina`**.

> **Estudantes** cursam disciplinas, que são lecionadas por um docente cada uma.

<img src="../../.gitbook/assets/file.excalidraw (3).svg" alt="" class="gitbook-drawing">

A partir dessa leitura, analisamos: existe associação entre **`Docente`** e **`Estudante`**? Se as disciplinas cursadas pelos discentes são lecionadas por professores, supõe-se que há alguma associação entre estas entidades. Vamos partir para a análise das cardinalidades dos relacionamentos e das restrições de participação antes de alterar o diagrama.

### Step 3. Definir as cardinalidades dos relacionamentos

Conforme a descrição do mini-mundo, "**Estudantes** cursam disciplinas" e "Uma **disciplina** é cursada por vários estudantes". Percebe-se que o estudante cursa, no mínimo, uma disciplina, e pode cursar mais de uma ao mesmo tempo; assim, a cardinalidade mínima é 1 e a cardinalidade máxima é N.

{% hint style="warning" %}
Não esqueça: marcamos as cardinalidades **do lado oposto** (sentido da seta em <mark style="color:blue;background-color:blue;">**azul**</mark> nas figuras abaixo).
{% endhint %}

<img src="../../.gitbook/assets/file.excalidraw (21).svg" alt="" class="gitbook-drawing">

Nessa imagem abaixo, expressamos a associação entre disciplina e estudante: no mínimo, uma disciplina pode ser cursada por _nenhum_ estudante (cardinalidade mínima _0_) e, no máximo, _vários_ estudantes (cardinalidade máxima _N_).

<img src="../../.gitbook/assets/file.excalidraw (20).svg" alt="" class="gitbook-drawing">

Assim, as cardinalidades ficam conforme a figura a seguir:

<img src="../../.gitbook/assets/file.excalidraw (28).svg" alt="" class="gitbook-drawing">

## Referências

*
