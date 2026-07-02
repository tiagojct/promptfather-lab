# Exercício 1 — Terminal essencial

## Objectivo

Ganhar à-vontade com o terminal — navegar, inspecionar e manipular ficheiros em segurança —
antes de envolver o agente de IA. Não precisas de decorar nada: precisas de reconhecer o
padrão quando o vires outra vez.

## Antes de começar

- Estás dentro do Codespace, com o VS Code aberto no navegador.
- O painel do terminal está visível em baixo (foi aberto automaticamente).

Se o terminal estiver fechado: menu **View → Terminal**, ou `` Ctrl + ` ``.

## O cenário

A Rosa (a mesma da deck) vai começar a explorar um dataset clínico com o agente. Antes disso,
quer perceber onde está tudo e confirmar que os dados são o que espera — exactamente o que
vamos fazer agora, à mão, sem o agente.

## Passos

### 1. Onde estou?

```bash
pwd
```

Devias ver algo como `/workspaces/<nome-do-repo>`. `pwd` significa *print working directory*
— "diz-me em que pasta estou". É o primeiro comando a correr sempre que te sentes perdido.

### 2. O que há aqui?

```bash
ls
```

Lista o conteúdo da pasta actual. Devias ver `files/` entre outras coisas.

Com mais detalhe (tamanhos, datas, ficheiros ocultos que começam por `.`):

```bash
ls -la
```

### 3. Entrar e sair de pastas

```bash
cd files
pwd
```

`cd` (*change directory*) move-te para dentro. Repara que `pwd` agora mostra `.../files`.

Para voltar atrás, duas formas que fazem o mesmo:

```bash
cd ..
cd files
cd -
```

`cd ..` sobe um nível (a pasta "mãe"). `cd -` volta à última pasta onde estiveste — útil
quando andas às voltas entre duas pastas.

### 4. Espreitar um ficheiro sem o abrir todo

Ainda dentro de `files/`:

```bash
head coorte-clinica.csv
```

`head` mostra as primeiras 10 linhas. Repara nos cabeçalhos das colunas e em algumas linhas
de exemplo. Para as últimas linhas, o equivalente é `tail coorte-clinica.csv`.

### 5. Contar

```bash
wc -l coorte-clinica.csv
```

`wc -l` conta linhas (*word count*, com a opção "linhas"). O nº de doentes é o resultado menos
1 — a primeira linha é o cabeçalho, não um doente.

### 6. Procurar dentro do ficheiro

```bash
grep "Hospital de Faro" coorte-clinica.csv
```

`grep` mostra só as linhas que contêm o texto que procuras. Não abriste o ficheiro num
editor, não fizeste scroll — pediste exactamente o que querias.

### 7. Copiar em segurança

Antes de qualquer teste que possa alterar um ficheiro, copia-o primeiro:

```bash
cp coorte-clinica.csv coorte-copia.csv
ls
```

`cp origem destino` copia. Agora tens duas cópias — podes experimentar na `coorte-copia.csv`
sem risco para o ficheiro original.

### 8. Limpar

```bash
rm coorte-copia.csv
ls
```

`rm` apaga — **sem reciclagem, sem confirmação.** Por isso copiamos primeiro e só apagamos a
cópia. Nunca corras `rm` num ficheiro se não tiveres a certeza absoluta de qual é.

### 9. Voltar à raiz

```bash
cd ..
pwd
```

Devias estar de novo em `/workspaces/<nome-do-repo>` — pronto para o Exercício 2.

## Output esperado

Ao fim deves conseguir, sem hesitar:

- Saber em que pasta estás e mover-te entre pastas (`pwd`, `cd`, `cd ..`, `cd -`).
- Listar o conteúdo, com e sem detalhe (`ls`, `ls -la`).
- Espreitar um ficheiro sem o abrir todo (`head`, `tail`).
- Contar linhas e procurar texto (`wc -l`, `grep`).
- Copiar antes de testar, e apagar só o que é seguro apagar (`cp`, `rm`).

## Para discussão

- O que muda entre `ls` e `ls -la`? Porque é que os ficheiros ocultos existem?
- Porque é que `head` é melhor do que abrir o CSV inteiro num editor, quando o ficheiro tem
  milhares de linhas?
- Se corresses `rm coorte-clinica.csv` por engano (o original, não a cópia), o que perderias?
  Como evitas isso no teu trabalho a sério?

## Queres ir mais além? (opcional)

Duas ideias que combinam comandos — a base de "scripts" de uma linha:

```bash
cd files
grep "Hospital de Faro" coorte-clinica.csv | wc -l   # conta SÓ as linhas de Faro
head -3 coorte-clinica.csv > amostra.csv              # guarda as 3 primeiras linhas num ficheiro novo
```

O símbolo `|` ("pipe") liga a saída de um comando à entrada do seguinte — aqui, `grep`
filtra e `wc -l` conta o que sobrou. O símbolo `>` grava a saída num ficheiro novo em vez de
a mostrar no ecrã.

**Mini-desafio:** usa `grep` + `|` + `wc -l` para descobrires quantos doentes são do
**Hospital de Braga**. (Repara: um `grep` de texto simples não distingue colunas — se
procurasses uma palavra que aparecesse em mais do que uma coluna, contarias de mais. Hospitais
são seguros porque o nome só aparece nessa coluna.) Depois apaga o `amostra.csv` — foi só
para praticar.
