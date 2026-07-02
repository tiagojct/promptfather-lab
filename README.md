# The Promptfather — ambiente pronto (Codespaces)

Este Codespace já traz o **opencode** instalado, e também **Python** com `pandas`, `scipy`
e `python-docx` (usados no Exercício 3, para gerar relatórios em Word). Não precisas de
instalar nada no teu computador nem criar conta em lado nenhum. Os ficheiros do curso estão
em [`files/`](files/) e os exercícios em [`exercicios/`](exercicios/).

Ao lado deste README já deve estar aberto o `exercicios/01-terminal.md`, **em modo de
pré-visualização** — vês o texto formatado (títulos, comandos em caixas cinzentas), não o
markdown em bruto com `#` e ```` ``` ````. Se abrires outro ficheiro `.md` da pasta
`exercicios/` pelo explorador (barra lateral esquerda), abre da mesma forma, já formatado.
Segue os exercícios por ali, um de cada vez — não precisas do browser para isso (mas os
links para `/setup` e `/lab`, quando aparecem, são mesmo para abrir no browser).

## Arrancar (3 passos)

1. **Copiar a chave da aula.** Abre `promptfather.tiagojct.eu/setup`, escreve o código que o
   formador mostra no ecrã, e copia a **chave** que aparece (só o valor). Não a colas ainda —
   é para o próximo passo.
   > Se o browser recusar colar (erro *"Unable to read from the browser's clipboard"*), usa o
   > atalho do teclado em vez de um botão de colar — `Cmd+V` no Mac, `Ctrl+Shift+V` no
   > terminal em Linux/Windows. Normalmente resolve sem precisar de mexer em permissões.
2. **Arrancar o agente e ligar a chave:**
   ```bash
   opencode
   ```
   Escolhe o provider **openrouter**. Quando pedir a **API key**, cola a chave que copiaste
   no passo 1. Depois escolhe um modelo. Recomendado por omissão:
   [`google/gemini-2.5-flash-lite`](https://openrouter.ai/google/gemini-2.5-flash-lite) —
   o mais barato, contexto enorme. Todos os modelos recomendados (com preço e link) estão
   na página `/setup`.
3. **Primeiro pedido:**
   ```
   Read files/coorte-clinica.csv. Tell me how many rows and columns it has and
   the type of each column.
   ```

## Os exercícios

Os 10 exercícios (5 núcleo + 5 extra/trabalho de casa) estão em dois sítios, com o mesmo
conteúdo — usa o que for mais prático no momento:

- **Aqui dentro**, em [`exercicios/`](exercicios/) — em pré-visualização, sem precisares do
  browser. Bom para seguires ao teu ritmo dentro do Codespace.
- **No browser**, em **promptfather.tiagojct.eu/curso** — a mesma coisa, com um "spoiler" de
  respostas no Exercício 4 e a navegação entre núcleo/extra mais visual.

Os ficheiros que os exercícios usam já estão todos aqui, na pasta `files/`.

## Ficheiros

- `files/coorte-clinica.csv` — dataset clínico sintético, 500 doentes. Tem problemas de
  qualidade propositais (valores em falta, categorias inconsistentes, idades impossíveis,
  datas mistas) — é para os encontrares no Exercício 3.
- `files/prompts.md` — prompts de exemplo para os exercícios.
- `files/hansen2024-asthma-biologics.pdf` — artigo científico real (Hansen et al., *CHEST*
  2024, acesso aberto CC BY) sobre remissão clínica em asma grave — usado no Exercício 4.

## Como abrir este ambiente

No repositório-modelo: **Code → Codespaces → Create codespace on main**. Em ~1–2 min tens o
opencode pronto, com estes ficheiros já dentro.

> A chave é da aula e é revogada no fim. Nunca envies dados identificáveis de doentes para a
> cloud — para isso, usa um modelo local (Ollama). Ver o Exercício 7 para pseudonimização e
> modelo local.
