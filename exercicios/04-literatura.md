# Exercício 4 — Trabalho com literatura

## Objectivo

Usar o agente para pesquisar artigos científicos, extrair informação-chave de um PDF real (e confirmar contra o texto original), e produzir uma lista de referências formatada.

## Antes de começar

- OpenCode configurado.
- O ficheiro `files/hansen2024-asthma-biologics.pdf` (artigo real, acesso aberto, licença
  CC BY) — vais usá-lo no passo 3.

## Passos

### 1. Pesquisa estruturada

Lança o OpenCode na raiz do projecto:

```bash
opencode
```

Faz uma pesquisa estruturada:

```
Search the literature for five recent articles (last five years) on the impact
of urban air pollution on lung function in children and adolescents.
For each article, give me:
- Authors (first three + et al. if more).
- Year.
- Title.
- Journal.
- DOI.
```

### 2. Verifica as referências (passo obrigatório, não opcional)

**Não confies cegamente.** Antes de avançar, confirma no PubMed ou no Google Scholar, para
**pelo menos um** dos cinco artigos:

- O DOI existe.
- Os autores estão correctos.
- O título não foi inventado.

Se encontrares uma referência inventada (alucinação), regista. É uma das discussões do dia —
não avances para o passo 4 sem teres feito esta verificação pelo menos uma vez.

### 3. Extrair informação de um PDF real

Pede ao agente:

```
Read the file files/hansen2024-asthma-biologics.pdf and extract:
- Research question.
- Study design.
- Sample size.
- Main variables (exposures and outcomes).
- Key results (concrete numbers, not generalities).
- Limitations the authors acknowledge.
```

Confirma cada um destes itens directamente no PDF, abrindo-o no VS Code (carrega duas vezes
no ficheiro) — **não confies na extração sem olhar para o original.**

<details>
<summary>Não abras isto antes de teres a tua própria resposta (respostas reais do artigo)</summary>

- **Pergunta de investigação:** quantos doentes com asma grave tratados com biológicos atingem
  remissão clínica, e o que prediz a resposta ao tratamento.
- **Desenho:** coorte observacional nacional (Danish Severe Asthma Register).
- **Tamanho da amostra:** 501 doentes *biologic-naive*.
- **Resultados principais:** 397 (79%) tiveram resposta clínica; destes, 97 (24%) atingiram
  remissão clínica — 19% da amostra total. Remissão foi predita por menor duração da doença e
  menor IMC.
- Se o agente disse números diferentes destes, é uma alucinação — regista-a.

</details>

### 4. Lista de referências formatada

Pega nas referências que sobreviveram à verificação do passo 2:

```
Format these five references in Vancouver style, ready to paste into a
bibliography section.
```

## Output esperado

- Cinco referências formatadas em Vancouver.
- Pelo menos uma verificada como existente (autores, título, DOI conferidos).
- Um resumo estruturado do artigo Hansen 2024, conferido contra as respostas reais.

## Para discussão

- Quantas referências precisaste de descartar por estarem incorrectas ou inventadas?
- O agente extraiu correctamente os números do PDF? Em que pontos é que falhou?
- Em que tarefas de literatura é que **confiarias** num agente sem verificar? Em quais é que **não** confiarias nunca?

## Queres ir mais além? (opcional)

Aqui só verificaste **uma** referência. Para uma verificação completa das cinco — e para
veres qual a taxa real de alucinação — faz o
[Exercício 8 — Verificar citações a sério](08-citacoes.md).
