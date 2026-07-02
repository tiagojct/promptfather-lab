# Exercício 9 — Criticar texto gerado (extra)

> **Extra.** Não é preciso terminar na sessão — podes fazer isto em casa. Aprofunda o
> Exercício 5: aqui o texto é maior e a revisão é mais estruturada.

## Objectivo

Praticar uma revisão crítica rigorosa de um texto científico gerado por IA — mais longo e
mais exigente do que o parágrafo de métodos do Exercício 5.

## Antes de começar

- Exercício 5 terminado.

## Passos

### 1. Gera um texto mais longo e mais arriscado

```
Using the dataset files/coorte-clinica.csv and the data-quality problems we
identified, write a "Results" section (~250 words) and a "Discussion" section
(~200 words) for a respiratory epidemiology article. Include concrete numbers
from the descriptive statistics. The Discussion should situate the results
against the existing literature on lung function and smoking.
```

A secção de Discussion é onde os modelos mais exageram — ao "situar face à literatura" sem
teres dado literatura nenhuma, o agente tem de inventar contexto.

### 2. Checklist de revisão estruturada

Para cada frase do texto gerado, classifica-a numa destas categorias:

- **✅ Verificável e correcta** — bate certo com o que calculámos.
- **⚠️ Overclaiming** — tecnicamente não está errado, mas usa linguagem mais forte do que os
  dados justificam ("prova", "demonstra claramente", "sem dúvida").
- **❌ Inventado** — número, referência ou afirmação que não vem de lado nenhum que
  reconheças.
- **🤔 Não verificável por mim** — precisarias de mais conhecimento de domínio para saber.

Conta quantas frases caíram em cada categoria.

### 3. Reescreve as piores três

Escolhe as três frases mais problemáticas e reescreve-as tu, à mão, para a versão que
aceitarias assinar.

### 4. Pede ao agente para se auto-rever

```
Re-read the text you generated. Point out yourself the sentences where the
language is more confident than the data supports, and rewrite them more
cautiously.
```

Compara a autocrítica do agente com a tua. Coincidem?

## Output esperado

- O texto original gerado.
- A tabela de classificação frase-a-frase (ou por categoria, com contagens).
- As três frases reescritas por ti.

## Para discussão

- O agente foi melhor a **gerar** ou a **rever-se a si próprio**?
- Overclaiming é mais perigoso do que inventar um número? Porquê?
- Que secção de um artigo (Métodos, Resultados, Discussão, Introdução) confiarias menos a um
  agente sem revisão? Porquê essa e não outra?
