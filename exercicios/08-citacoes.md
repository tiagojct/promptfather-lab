# Exercício 8 — Verificar citações a sério (extra)

> **Extra.** Não é preciso terminar na sessão — podes fazer isto em casa. Aprofunda o
> Exercício 4: aqui verificas **todas** as referências, não só uma.

## Objectivo

Medir, com números reais, a taxa de alucinação de referências de um modelo — e construir o
hábito de verificação sistemática antes de citar algo que um agente encontrou.

## Antes de começar

- Exercício 4 terminado (já tens cinco referências geradas).
- Acesso à internet para consultar PubMed / Crossref / Google Scholar.

## Passos

### 1. Reúne as cinco referências

Usa as do Exercício 4, ou gera um novo conjunto:

```
Search the literature for five recent articles on [pick a topic from your
clinical area]. For each one: Authors, Year, Title, Journal, DOI.
```

### 2. Verifica cada uma, uma a uma

Para **cada** referência, tenta confirmar em <https://pubmed.ncbi.nlm.nih.gov> ou
<https://search.crossref.org>:

| # | DOI existe? | Autores correctos? | Título correcto? | Veredicto |
|---|---|---|---|---|
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |
| 4 | | | | |
| 5 | | | | |

Marca o veredicto de cada uma: **real e correcta** / **real mas com erro** (ex.: ano errado,
autor a mais) / **inventada**.

### 3. Calcula a tua taxa

Quantas das cinco eram 100% reais e correctas? Isso é a tua "taxa de confiança" para este tipo
de pedido, com este modelo, hoje. (Vai mudar com outro modelo, outro tema, outro dia.)

### 4. Pede ao agente para se corrigir

```
Of these five references, the following were incorrect or I couldn't find them:
[list]. Find verifiable substitutes for those, on the same topic.
```

Verifica as novas também — não presumas que a segunda tentativa é melhor sem checar.

## Output esperado

- A tabela de verificação preenchida para as 5 referências.
- Uma taxa de acerto (ex.: "3 em 5 corretas de início").

## Para discussão

- Isto mudou a tua confiança em usar um agente para revisões de literatura?
- Achas que esta taxa seria diferente com um modelo pago, maior? Vale a pena testar
  (Exercício 6)?
- Que regra pessoal vais adoptar a partir de agora antes de citares algo que um agente
  encontrou?
