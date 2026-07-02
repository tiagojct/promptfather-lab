# Exercício 6 — Comparar modelos (extra)

> **Extra.** Não é preciso terminar na sessão — podes fazer isto em casa.

## Objectivo

Correr o mesmo pedido em modelos diferentes e comparar velocidade, qualidade e alucinações.
Ligar o que vimos na deck sobre tokens e custo a uma experiência concreta.

## Antes de começar

- Exercício 3 terminado (o prompt de qualidade de dados que vais reutilizar).
- OpenCode configurado com acesso à chave da aula (todos os modelos abaixo estão disponíveis
  com ela).

## Passos

### 1. Escolhe dois ou três modelos

Usa os quatro recomendados em **promptfather.tiagojct.eu/setup/&lt;código&gt;** — são todos
pagos mas baratos, escolhidos para cobrir um espectro de preço/qualidade/velocidade:

| Modelo | Contexto | Preço (entrada/saída por 1M tokens) | OpenRouter |
|---|---|---|---|
| `google/gemini-2.5-flash-lite` | 1M | $0.10 / $0.40 | [ver →](https://openrouter.ai/google/gemini-2.5-flash-lite) |
| `openai/gpt-4o-mini` | 128K | $0.15 / $0.60 | [ver →](https://openrouter.ai/openai/gpt-4o-mini) |
| `deepseek/deepseek-chat-v3.1` | 164K | $0.21 / $0.79 | [ver →](https://openrouter.ai/deepseek/deepseek-chat-v3.1) |
| `anthropic/claude-haiku-4.5` | 200K | $1.00 / $5.00 | [ver →](https://openrouter.ai/anthropic/claude-haiku-4.5) |

Escolhe 2-3 (sugestão: o mais barato, um do meio, e o Haiku para veres se a diferença de
preço se sente na qualidade).

### 2. Corre o mesmo prompt em cada um

Dentro do OpenCode, muda de modelo (normalmente `/model` ou reinicia com outro), e em cada um
corre exactamente o mesmo pedido do Exercício 3:

```
In files/coorte-clinica.csv, identify data-quality problems: missing values (per
column and concentration), inconsistent categories, implausible values (ages,
fev1), and mixed date formats. List each problem with concrete examples of the
affected rows.
```

Anota, para cada modelo:

- Quanto tempo demorou a responder (aproximado).
- Quantos dos problemas reais (ver Exercício 3) encontrou.
- Se inventou algum problema que não existe.

### 3. Compara os tokens e calcula o custo real

Se o OpenCode mostrar o nº de tokens usados (input/output) por pedido, anota-os. Depois,
usando os preços da tabela do passo 1, calcula quanto custou **este único pedido** em cada
modelo:

```
custo = (tokens de entrada / 1 000 000 × preço de entrada) + (tokens de saída / 1 000 000 × preço de saída)
```

Não te assustes com o resultado — este pedido inteiro, num modelo destes, custa tipicamente
frações de cêntimo. É por isto que "pago" não significa "caro": significa que alguém tem de
saber, ao certo, quanto custa cada pedido — e agora sabes fazer essa conta.

### 4. Tabela de comparação

Pede ao próprio agente para te ajudar a montar a tabela final, ou fá-la à mão:

| Modelo | Tempo | Problemas encontrados | Alucinou? | Custo deste pedido |
|---|---|---|---|---|
| ... | ... | ... | ... | ... |

## Output esperado

- Uma tabela comparando pelo menos 2 modelos no mesmo prompt, com o custo calculado.
- Uma conclusão pessoal: qual escolherias para este tipo de tarefa, e porquê.

## Para discussão

- O modelo mais rápido foi também o mais correcto?
- Achas que vale a pena pagar por um modelo melhor para trabalho clínico a sério? Em que
  situações sim, em que situações não?
- Se tivesses de escolher **um único modelo** para usar sempre, qual seria e porquê?
