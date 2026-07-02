# Exercício 2 — Instalar e configurar o OpenCode

## Objectivo

Instalar o OpenCode, dar-lhe a **chave do curso**, escolher um modelo (pago, mas muito barato — a chave já tem saldo) e fazer o primeiro *prompt* a um agente de IA. **Não precisas de criar conta em lado nenhum.**

## Antes de começar

- Exercício 1 terminado — sabes mover-te no terminal.
- O **código do curso** (o instrutor mostra-o no ecrã).
- Se ainda não escolheste como correr o opencode, vai a **promptfather.tiagojct.eu/lab** —
  recomendamos o **GitHub Codespaces** (conta gratuita, criada em segundos; ambiente já pronto
  em ~2 minutos). Instalar no teu computador é uma alternativa, não a via principal.
- **Precisas de uma conta GitHub para o Codespaces** (não precisas para as outras duas vias).
  Se ainda não tens: vai a <https://github.com/signup>, escreve o teu email, escolhe uma
  password e um nome de utilizador, confirma o email — é gratuito e demora menos de um minuto.
  Não é preciso cartão de crédito nem nenhuma configuração extra para usar o Codespaces.

## Passos

### 1. Instalar o OpenCode

No Codespace já vem instalado (confirma com o passo abaixo). Se estiveres no teu computador:

```bash
npm install -g opencode-ai
```

A instalação demora cerca de 30 segundos. Quando terminar:

```bash
opencode --version
```

Deves ver uma versão. Se vires `command not found`, fala com o instrutor.

### 2. Obter a chave do curso

Não precisas de conta no OpenRouter — a chave é fornecida para a aula.

1. Abre **promptfather.tiagojct.eu/setup** num separador novo.
2. Escreve o **código do curso** (o que está no ecrã).
3. Copia a **chave** (só o valor, não uma linha de comando).

> **A chave é da aula e é revogada no fim.** É um segredo: não a partilhes fora daqui nem a fazes *commit* para o Git.
> Não colas a chave em lado nenhum ainda — o `opencode` vai pedi-la directamente daqui a
> pouco (passo 4).

### 3. Escolher um modelo

Estes são pagos (por token), mas muito baratos — a chave da aula já tem saldo para o dia todo.
Vê a lista completa e atualizada em **promptfather.tiagojct.eu/setup/&lt;código&gt;** (tem
sempre o link "ver no OpenRouter" a seguir a cada um). Recomendados para hoje:

1. `google/gemini-2.5-flash-lite` — **recomendado por omissão**: o mais barato, janela de
   contexto enorme (1M tokens). [ver no OpenRouter](https://openrouter.ai/google/gemini-2.5-flash-lite)
2. `openai/gpt-4o-mini` — muito testado, fiável a usar ferramentas.
   [ver no OpenRouter](https://openrouter.ai/openai/gpt-4o-mini)
3. `deepseek/deepseek-chat-v3.1` — ótimo raciocínio pelo preço.
   [ver no OpenRouter](https://openrouter.ai/deepseek/deepseek-chat-v3.1)
4. `anthropic/claude-haiku-4.5` — mais caro dos quatro, mas nitidamente mais capaz; ainda barato.
   [ver no OpenRouter](https://openrouter.ai/anthropic/claude-haiku-4.5)

Escolhe um. Podes trocar depois — é só relançar o `opencode` e escolher outro.

### 4. Lançar o OpenCode e ligar a chave

```bash
opencode
```

Na primeira vez, o OpenCode pergunta:

- **Provider** — escolhe `openrouter`.
- **API key** — cola aqui a chave que copiaste no passo 2.
- **Model** — cola o nome do modelo (por exemplo `google/gemini-2.5-flash-lite`).

### 5. Primeiro *prompt*

Dentro do OpenCode, escreve:

```
List the files and folders in this project and explain, in two sentences per item, what each one does.
```

> **A partir daqui, as prompts que colas no agente estão em inglês** (o texto à volta,
> como este, continua em português). Não é preciso saber inglês fluente — é copiar e colar.
> Escrevemos as prompts em inglês porque os modelos tendem a responder com mais precisão e
> menos erros nessa língua: a maior parte do treino e da documentação técnica está em inglês,
> e é também a língua universal do código e da terminologia clínica internacional.

Espera pela resposta.

## Output esperado

- O agente reconhece a estrutura do projecto.
- A descrição é breve e plausível.
- Se o agente alucinar (inventar ficheiros que não existem), notas. Falamos disso na discussão.

Para sair do OpenCode: `Ctrl+C` ou escreve `/exit`.

## E se eu quiser a minha própria conta? (opcional)

Não é preciso hoje. Mas para uso teu, depois do curso: cria conta gratuita em
<https://openrouter.ai>, vai a **Keys → Create Key**, e usa essa chave em vez da do curso.
Alguns modelos são gratuitos; os melhores cobram por *token*.

## Para discussão

- Que diferenças notaste entre os dois modelos, se experimentaste ambos?
- O agente descreveu correctamente o que cada pasta contém? Inventou alguma coisa?
- Que critérios pesariam mais na escolha de modelo se isto fosse investigação a sério?
