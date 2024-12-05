# Documentação do Projeto CENSO_RAIS

## Introdução

Este documento orientativo apresenta a forma em que o Projeto Inep e SoU Ciência manterá a documentação de todo o trabalho desenvolvido no decorrer de todo este processo. É um guia para que toda a equipe tenha norteada a forma de manter a documentação do projeto estruturada.

### Objetivo

Orientar a equipe do projeto no desenvolvimento do processo de documentação deste trabalho de cruzamento dos dados do CENSO 2017 e RAIS 2018 para que se possa replicar para outros anos as mesmas ações, trazendo um resultado padronizado.

Este processo visa garantir uma documentação clara e precisa de todos os códigos, procedimentos e resultados. Isso será essencial para garantir a reprodutibilidade e continuidade do projeto.

Devido a restrição de rede, o GIT está instalado localmente na VM para controle de versão dos códigos e scripts gerados. Cada membro da equipe é responsável por versionar suas alterações e manter um histórico claro dos objetos criados, sejam eles códigos, scripts, tabelas, entre outros.


### Sobre este documento

Este documento:
- está em formato Markdown. Saiba como utilizar este formato consultando [docs/markdown.md](docs/markdown.md)
- usa a ferramenta Git. O [docs/git.md](docs/git.md) será o arquivo de refências rápidas sobre o uso do Git.



## Configuração

### Repositório principal
- Repositório principal: `P:\_work.git`
- Branch principal: `dev`

Estrutura:

```
/_work.git/
    ├── /scripts_pentaho/
    ├── /scripts_python/
    ├── /scripts_r/
    ├── /scripts_sql/
```


### Criação dos repositórios individuais

1. Clique com o botão direito na área Desktop, e escolha o Git Bash.
2. Dê o comando `git clone P:\_work.git`. Será criada a pasta `_work.git` em seu Desktop.
3. Puxe o conteúdo do repositório `P:\_work.git` usando o comando `git pull origin dev`
4. Entre no branch `dev` com o comando `git branch dev`


## Rotinas

### Rotina de trabalho
1. Puxe o conteúdo do repositório `P:\_work.git` usando o comando `git pull origin dev --rebase`. Sempre use a flag `--rebase`
2. Adicione as suas modificações usando `git add` e `git commit`
3. Envie para `P:\_work.git` usando `git push origin dev`

> Neste fluxo de trabalho use apenas o branch `dev`

Se o comando for rejeitado, significa que que o repositório principal possui trabalho salvo que você não possui em seu repositório local. Neste caso, antes de enviar, você precisa atualizar o seu repositório com o git pull. Seu trabalho não será perdido, porem, se houver uma atualização paralela no mesmo arquivo que você está tentando atualziar, o git pedirá que você resolva o conflito de versões primeiro.

#### Fluxos paralelos

Quando dois ou mais colaboradores estão trabalhando em um mesmo recurso precisam compartilhá-lo, eles podem trocar ramificações diretamente entre si, adicionando o caminho diretamente para o repositório do colega.

```
git remote add repo-fulano P:\...
```

O push, nestes casos, será:
```
git push repo-fulano nome-do-branch
```
O colaboador verifica o recebimento da ramificação usando `git brach`, e a partir da ramificação recebida, continua o seut trabalho. O último a atualizar é quem envia para o repositório principal.


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


> "Adiciona extracao_dados_censo_2024_12.py"

> "Altera a função convert_number em extracao_dados_censo_2024_12.py"

> "Renomeia a variável ABC para XYZ"


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



