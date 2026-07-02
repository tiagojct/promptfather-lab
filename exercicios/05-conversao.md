# Exercício 5 — Conversão de ficheiros e redacção

## Objectivo

Usar o agente para tarefas de "limpeza" que normalmente consomem tempo: converter formatos de ficheiro e redigir um parágrafo de métodos baseado na análise que já fizeste.

## Antes de começar

- Exercício 3 terminado — já exploraste o dataset e sabes os problemas de qualidade.
- OpenCode configurado.

## Passos

### 1. Converter CSV para XLSX

Lança o OpenCode na raiz do projecto e pede:

```
Convert the file files/coorte-clinica.csv to an Excel file (.xlsx) with the same
name, in the same folder. Make sure the date columns are recognised as dates
in Excel.
```

Confirma que o ficheiro `coorte-clinica.xlsx` foi criado:

```bash
ls files/
```

### 2. Redigir um parágrafo de métodos

```
Using what you found out about the dataset files/coorte-clinica.csv, write me a
methods paragraph for a "Population and data sources" section of an
epidemiology article. The paragraph should:
- Describe the sample (size, age range, sex distribution).
- Mention the main variables we used.
- Honestly acknowledge the sample's limitations that you identified (hospital
  bias, absence of socioeconomic variables, etc.).
- Be between 150 and 200 words.
- Be in academic English, past tense, passive voice where appropriate.
```

Lê o parágrafo gerado com cuidado. **Não o aceites tal como sai.**

### 3. Guardar o parágrafo em Markdown

Pede ao agente:

```
Save that paragraph to a new file: methods.md
```

Confirma:

```bash
cat methods.md
```

### 4. Checklist de autorevisão (obrigatório, não só discussão)

Antes de dares o exercício por terminado, relê o `methods.md` e responde por escrito
(numa nota tua, não precisa de ir ao agente) a cada item:

- [ ] **Precisão**: todos os números (tamanho da amostra, idades, %) batem certo com o que
      calculámos no Exercício 3?
- [ ] **Certeza excessiva**: há alguma frase que soa mais confiante do que os dados permitem
      (ex.: "demonstra" em vez de "sugere")?
- [ ] **Estatísticas inventadas**: alguma percentagem ou valor que não calculámos e que o
      agente "preencheu" sozinho?
- [ ] **Limitações**: as limitações reais do dataset (enviesamento de hospital, dados em
      falta) estão lá, ou foram suavizadas/omitidas?

Se marcaste algum problema, pede ao agente para corrigir especificamente esse ponto — não
peças só "melhora o parágrafo".

### 5. Converter o Markdown para PDF (opcional)

Se tiveres o Quarto instalado (confirma com `quarto --version`), sai do OpenCode (`/exit`) e
corre no terminal:

```bash
quarto render methods.md --to pdf
```

Vai aparecer um ficheiro `methods.pdf` na mesma pasta. Se não tiveres Quarto, o `methods.md`
chega — não é obrigatório converter para PDF.

## Output esperado

- `coorte-clinica.xlsx`.
- `methods.md`, com a checklist de autorevisão preenchida.
- `methods.pdf`, se tiveres Quarto.

## Para discussão

- O parágrafo gerado reflectiu honestamente as limitações que identificaste, ou suavizou demasiado?
- Encontraste no texto alguma afirmação **factualmente errada** sobre o dataset?
- Há alguma parte deste parágrafo que copiarias literalmente para um manuscrito teu? Qual? Porquê?
- O que **nunca** devias deixar o agente decidir sozinho sobre métodos?

## Queres ir mais além? (opcional)

Repete o passo 4 (checklist) num parágrafo mais exigente: pede ao agente um parágrafo de
**Discussão** (não só Métodos) de ~150 palavras, incluindo uma frase sobre limitações e uma
sobre implicações clínicas. A linguagem de "certeza excessiva" costuma aparecer mais aqui do
que em Métodos — repara se acontece.
