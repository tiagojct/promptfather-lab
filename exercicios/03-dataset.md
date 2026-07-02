# Exercício 3 — Exploração crítica de um dataset, em Python

## Objectivo

Usar o agente para explorar um CSV clínico **em Python (pandas)**, calcular estatísticas
descritivas, identificar pelo menos três problemas de qualidade dos dados, e gerar um
relatório em Word (Tabela 1 + teste de hipótese) e um abstract em Word.

## Antes de começar

- Exercício 2 terminado — o OpenCode está configurado com um modelo.
- Estás na raiz do projecto (`pwd` mostra `/workspaces/...`).
- O Codespace já vem com **Python**, e os pacotes `pandas`, `scipy` e `python-docx` instalados.
  Não precisas de instalar nada.

## O dataset

`files/coorte-clinica.csv` — cerca de 500 doentes, dados sintéticos sobre função pulmonar e asma.

**Os dados foram propositadamente sujados.** A tua tarefa é descobrir como.

## Passos

### 1. Espreita o ficheiro à mão primeiro

Antes de envolver o agente, percebe por ti:

```bash
head files/coorte-clinica.csv
wc -l files/coorte-clinica.csv
```

Anota numa nota mental: quantas linhas tem? Quantas colunas?

### 2. Confirma o Python e lança o OpenCode

```bash
python3 --version
opencode
```

Deves ver uma versão do Python. Se vires `command not found`, fala com o instrutor.

### 3. Pede ao agente uma descrição geral, em Python

```
Using Python and pandas, read files/coorte-clinica.csv into a DataFrame. Tell me:
- How many rows and columns it has.
- The column names and, for each one, the dtype pandas assigned (numeric,
  object, etc.).
- Show me the first six rows.
Write this as a short Python script I can re-run, not just a one-off answer.
```

### 4. Estatísticas descritivas e à caça de problemas, em Python

```
Still using pandas on files/coorte-clinica.csv:
- For each numeric column, compute mean, standard deviation, minimum, and maximum.
- For each categorical column, show a frequency table of the values (value_counts),
  including any missing or blank values as their own category.
- Report the percentage of missing values per column.

Then look at this dataset with a clinician's eye and point out every data-quality
problem you can find:
- Implausible or impossible values.
- Inconsistent coding of the same variable.
- Suspicious patterns in the distributions.
- Variables you would expect to see that are missing entirely.
- Any sign of selection bias.

Show me the Python code you used, not just the results.
```

### 5. Gera o relatório em Word — Tabela 1 e teste de hipótese

```
Write a Python script using pandas, scipy.stats and python-docx that reads
files/coorte-clinica.csv and creates report.docx containing:
1. A short introduction (2-3 sentences) describing the dataset.
2. A "Table 1" descriptive table, grouped by asthma_diagnosis, as a real Word
   table (mean/SD for numeric variables, count/% for categorical ones, one
   column per group).
3. A hypothesis test comparing fev1 between the asthma_diagnosis groups
   (scipy.stats.ttest_ind), with the p-value shown in the document.
4. One or two lines interpreting whether the difference is statistically
   significant.

Run the script and confirm report.docx was created.
```

Abre o `report.docx` (clica com o botão direito no explorador de ficheiros → "Download", ou
usa a extensão de preview do VS Code se a tiveres) e confere se a tabela e a interpretação
fazem sentido.

### 6. Gera o abstract em Word

```
Write a second Python script that uses python-docx to create abstract.docx: a
structured abstract (150-200 words) of what we found in
files/coorte-clinica.csv:
- Background (1 sentence): what this cohort is.
- Methods (1-2 sentences): sample size, key variables, the comparison tested
  in report.docx.
- Results (2-3 sentences): the actual numbers from the Table 1 and the p-value,
  not invented ones.
- Conclusion (1 sentence), appropriately cautious given this is a teaching dataset.

Run it and confirm abstract.docx was created.
```

### 7. Checklist de autorevisão do abstract (obrigatório)

Antes de dares o exercício por terminado, abre o `abstract.docx` e responde por escrito
(numa nota tua, não precisa de ir ao agente) a cada item:

- [ ] **Precisão**: os números do abstract (amostra, p-value, médias) batem certo com os
      que apareceram no `report.docx`?
- [ ] **Certeza excessiva**: há alguma frase mais confiante do que os dados permitem (ex.:
      "demonstra" em vez de "sugere")?
- [ ] **Estatísticas inventadas**: algum número que o agente "preencheu" sozinho, sem vir do
      cálculo real?
- [ ] **Limitações**: fica claro que isto é um dataset sintético de ensino, não um estudo real?

Se marcaste algum problema, pede ao agente para corrigir especificamente esse ponto.

## Output esperado

- Pelo menos **três** dos seguintes problemas de qualidade identificados:
  - Valores em falta concentrados num subgrupo específico.
  - Codificação inconsistente de uma variável categórica (`smoking_status` tem o mesmo
    valor escrito de várias formas diferentes).
  - Valores impossíveis (idades, medidas de função pulmonar).
  - Concentração desproporcional num hospital ou local.
  - Variáveis ausentes que seriam relevantes (rendimento, etnia, etc.).
  - Distribuição de sexo binária (sem outras categorias).
- `report.docx` — Tabela 1 (agrupada por `asthma_diagnosis`) com o p-value do teste de
  hipótese, e uma frase de interpretação.
- `abstract.docx` — abstract estruturado, com a checklist de autorevisão preenchida.

## Para discussão

- Que problemas é que o agente apontou imediatamente, e quais é que tu tiveste de o empurrar a procurar?
- Há algum problema que o agente **não** detectou? Porquê?
- Porque é que a Tabela 1 agrupa por `asthma_diagnosis` e não por `smoking_status`, apesar
  de `smoking_status` também ser clinicamente relevante?
- Se isto fosse um estudo real, que outro teste de hipótese pedirias ao agente para
  acrescentar ao relatório?

## Queres ir mais além? (opcional)

Pede ao agente um **plano de limpeza**, não só a lista de problemas:

```
Based on the problems we identified, propose a step-by-step cleaning plan for
this dataset (what to do for each problem, and what you should NOT do without
confirming with someone who knows the clinical domain). Then apply that plan
and export the result to files/coorte-clinica-limpa.csv, keeping the original
file intact.
```

Guarda o `coorte-clinica-limpa.csv` — vais precisar dele se fizeres o
[Exercício 7 — Privacidade e modelo local](07-privacidade.md).
