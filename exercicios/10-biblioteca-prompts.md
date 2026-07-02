# Exercício 10 — Construir a tua biblioteca de prompts (trabalho de casa)

> **Extra / trabalho de casa.** Este exercício não tem resposta certa — é para levares
> contigo depois do curso. Faz sentido fazê-lo com dados e perguntas da tua própria área.

## Objectivo

Sair do curso com **3 a 5 prompts reutilizáveis**, escritos por ti, para o teu trabalho real
— não os exemplos genéricos que usámos nos exercícios anteriores.

## Antes de começar

- Os Exercícios 1-5 terminados — já viste como um prompt bem escrito difere de um vago.
- (Idealmente) um ficheiro teu — um CSV, um conjunto de notas, um rascunho — que possas usar
  com segurança (sem dados identificáveis de doentes; se tiveres dúvidas, revê a secção da
  deck sobre a fronteira e pseudonimização).

## Porquê isto importa

Os prompts que usámos no curso (`files/prompts.md`) são genéricos, para ensinar o padrão. Um
prompt realmente útil é específico ao teu domínio: sabe que tipo de dados tens, que formato
de output precisas, e que erros comuns evitar.

## Passos

### 1. Identifica 3 a 5 tarefas repetidas do teu trabalho

Pensa em tarefas que fazes (ou farias) mais do que uma vez: resumir um artigo, rever
consistência de um dataset, redigir uma secção de um tipo específico, converter entre
formatos, preparar dados para uma ferramenta específica.

### 2. Escreve o primeiro rascunho de cada prompt

Para cada tarefa, escreve um prompt específico — não "resume este artigo" mas algo como:

```
Summarise this article about [area] in 150 words, for a [audience] readership,
always highlighting: study design, sample size, main result, and one
limitation. Never invent numbers — if they're not in the text, write
"not reported".
```

### 3. Testa cada prompt com o opencode

Corre cada prompt num caso real (ou no dataset do curso, se não tiveres o teu). Ajusta o
texto até o resultado ser consistentemente o que precisas — isto é o "prompt engineering" na
prática: iterar, não acertar à primeira.

### 4. Guarda a tua biblioteca

```bash
touch files/os-meus-prompts.md
```

Cola lá os prompts finais, com um título e uma frase de contexto para cada um (para te
lembrares, daqui a três meses, para que servia).

## Output esperado

- `files/os-meus-prompts.md` com 3 a 5 prompts testados e funcionais.
- Cada prompt específico ao teu domínio, não genérico.

## Para discussão (contigo próprio, ou com colegas depois)

- Qual destes prompts vais mesmo usar na próxima semana?
- Que regra de ouro (das que vimos: nunca dados identificáveis, verificar sempre, pedir
  tipos antes de conclusões) mais se aplica ao teu uso do dia-a-dia?
- Vale a pena partilhar esta biblioteca com colegas do teu serviço?
