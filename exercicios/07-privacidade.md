# Exercício 7 — Privacidade: pseudonimização e modelo local (extra)

> **Extra.** Não é preciso terminar na sessão — podes fazer isto em casa.

## Objectivo

Praticar duas defesas concretas da fronteira institucional que vimos na deck: **pseudonimizar
antes de enviar**, e **usar um modelo local** quando não é possível garantir a fronteira.

## Antes de começar

- Exercício 3 terminado (idealmente com o `coorte-clinica-limpa.csv` do "queres ir mais além").
- Se quiseres experimentar o modelo local: `Ollama` instalado (`ollama --version`). Se não
  tiveres, faz só a Parte A — a Parte B é opcional dentro do opcional.

## Parte A — Pseudonimização

### 1. Identifica o que identifica

```
In files/coorte-clinica.csv, which column serves as the patient's unique
identifier? If this dataset had a full name, address, or date of birth, which
of those columns should never leave the machine without being treated first?
```

### 2. Pseudonimiza

```
Create a copy of files/coorte-clinica.csv called files/coorte-clinica-pseudo.csv
where the patient_id column is replaced with a new sequential code (P-0001,
P-0002...) with no visible relation to the original value. Make sure the rest
of the columns stay the same.
```

Confirma que `patient_id` mudou mas as restantes colunas não:

```bash
head files/coorte-clinica.csv
head files/coorte-clinica-pseudo.csv
```

### 3. Discute a diferença

Pseudonimizar **não é** anonimizar — se guardares a tabela de correspondência entre o código
antigo e o novo, ainda é possível voltar atrás. Só é seguro se essa tabela nunca sair da tua
máquina (e mesmo assim, combinado com poucas variáveis, um doente pode ser reidentificável).

## Parte B — Modelo local (só se tiveres Ollama)

### 1. Instala um modelo pequeno

```bash
ollama pull llama3.2:3b
```

### 2. Corre a mesma tarefa, local

No OpenCode, muda o provider para `ollama` e o modelo para `llama3.2:3b`, depois repete:

```
Read files/coorte-clinica-pseudo.csv and tell me how many rows and columns
it has.
```

### 3. Compara

- Foi mais lento que a cloud? Quanto?
- A resposta foi tão boa como a de um modelo cloud maior?
- Que dados **nunca saíram da tua máquina** neste processo?

## Output esperado

- `files/coorte-clinica-pseudo.csv` criado, com `patient_id` pseudonimizado.
- Uma resposta escrita (2-3 frases) à pergunta: "quando é que pseudonimizar chega, e quando
  precisas mesmo de modelo local?"

## Para discussão

- Achas que pseudonimizar este dataset seria suficiente para o enviar para uma cloud
  americana? Que mais precisarias de saber (contrato, base legal) antes de decidir?
- O modelo local compensa a lentidão, para dados de doentes reais? Em que cenário sim, em
  que cenário não?
