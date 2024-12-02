# Documentação do Projeto CENSO_RAIS

## Introdução

Este documento orientativo apresenta a forma em que o Projeto Inep e SoU Ciência manterá a documentação de todo o trabalho desenvolvido no decorrer de todo este processo. É um guia para que toda a equipe tenha norteada a forma de manter a documentação do projeto estruturada.

### Objetivo

Orientar a equipe do projeto no desenvolvimento do processo de documentação deste trabalho de cruzamento dos dados do CENSO 2017 e RAIS 2018 para que se possa replicar para outros anos as mesmas ações, trazendo um resultado padronizado.

Este processo visa garantir uma documentação clara e precisa de todos os códigos, procedimentos e resultados. Isso será essencial para garantir a reprodutibilidade e continuidade do projeto.

Devido a restrição de rede, o GIT está instalado localmente na VM para controle de versão dos códigos e scripts gerados. Cada membro da equipe é responsável por versionar suas alterações e manter um histórico claro dos objetos criados, sejam eles códigos, scripts, tabelas, entre outros.


### Sobre este documento

Este documento:
- está em formato Markdown. Saiba como utilizar este formato consultando <docs/markdown.md>
- usa a ferramenta Git. O <docs/git.md> será o arquivo de refências rápidas sobre o uso do Git.



## Configuração inicial

O local escolhido para ser o repositório git é o diretório `P:\_work`. O procedimento será cada usuário manter uma pasta, em seu próprio usuário, que busca e envia conteúdo para este diretório. Local sugerido: ***Desktop***. Nome de pasta sugerido: ***work***.

### Criando seu repositório

1. iniciar um repositório. Local sugerido: Desktop. Nome da pasta à escolha.
```
git init
```

2. adicionar o caminho para o repositório `P:\_work` como *origin*
```
git remote add origin P:\_work
```

3. puxar o conteúdo do branch **dev**
```
git pull origin dev
```

## Organização

### Estrutura de Diretórios

Estrutura de diretórios adotado para o projeto

/_work/
    ├── /docs/
    ├── /scripts_pentaho/      
    ├── /scripts_python/
    ├── /scripts_r/
    ├── /scripts_sql/                     
    └── readme.md

Como cada usuário irá criar sua própria cópia do repositório principal, haverão múltiplas cópias dos mesmos arquivos no computador, é assim que deve ser. Por isso, deve-se prestar atenção em trabalhar com os arquivos corretos, ou seja, os que estão na sua pasta work do seu desktop. Procurar arquivos através do Pesquisar, abrirá brechas para abrir o arquivo errado.

### Nomeclatura dos arquivos

Os nomes dos arquivos devem:
- começar com palavras descritivas
- usar *underline*, como separador de palavras
- quando necessário, ter como sufixo a data nos formatos AAAA_MM_DD, ou AAAA_MM

Exemplos:

> extracao_censo_por_municipio_202310.sql

> cruzamento_rais2018_censo2017.py

### Formato dos comentários nos commits

 O comentário do commit no GIT deve descrever, com clareza, o que a sua atualização faz. Exemplos:

```
"Adiciona extracao_dados_censo_2024_12.py"
```

```
"Altera a função convert_number em extracao_dados_censo_2024_12.py"
```

```
"Renomeia a variável ABC para YZX"
```

O comando completo é:
```
git commit -m "mensagem"
```

### Documentação no cabeçalho dos códigos

Manter um cabeçalho de detalhamento nos códigos que identifique com informações básicas como: objetivo do script, autor e data. Pode acrescentar informações descritivas que auxiliem no entendimento do código e seu uso.

Exemplo:

```sql
-- Script para extração de dados do CENSO por município
-- Autor: João Silva
-- Data: 05/10/2024

SELECT * FROM censo_2017 WHERE municipio = 'XXXXX';
  
```

