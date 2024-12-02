# Básico do Git

## 1. Configuração inicial

Após a instalação, use os seguintes comandos no terminal para a configuração básica do git.

```shell
git config --global user.name "Ricardo Ireno"
git config --global user.email ireno.ricardo@unifesp.com
git config --global core.editor "editor-de-sua-preferencia"
```

Ao configurar `core.editor`, é preciso que o editor a ser usado esteja configurado na variável PATH do sistema, mas a maioria dos editores de código já faz isso na instalação. O VS Code, por exemplo, adiciona a variável "vscode".


## 2. Repositórios

**Inicializando**

```shell
git init
```

Com o repositório inicializado, se você pretende clonar outro repositório, use o comando ``git remote add endereco-do-repositorio`` para adicionar o endereço deste repositório.

Exemplo: 

Adicionando um repositório local:
```shell
git remote add D:\dev\repositorio
```

Adicionando um repositório que você criou no Github ou Gitlab:

```shell
git remote add git@github.com:seunickname/seurepositotio.git
```

## 3. O conceito de staging area e commited.

- **staging area:** área intermediária onde você prepara (stage) as alterações antes de confirmá-las (commit). 
- **commit:** é o registro das alterações no repositório. É como um "snapshot", um marco em uma linha do tempo.
- Qualquer arquivo que não foi adicionado ao registro, e também não está na staging area, são mostrados em vermelho.


#### Inserir arquivos no stage

```shell
git add nome-do-arquivo
```

#### Retirando um arquivo do stage

Um arquivo específico:
```shell
git reset nome do arquivo
```

Todos os arquivos:
```shell
git reset --
```

#### Gravar os arquivos no registro (commit)

```shell
git commit -m "mensagem"
```

#### Verificar o status do repositório

```shell
git status
```

#### Verificar o histórico de commits

```shell
git log
```

Apenas os três últimos:
```shell
git log -3
```

De um commit A  a um commit B:
```shell
git log A...B
```

De um autor específico:
```shell
git log --author=usuario
```

#### Para verificar as mudanças no conteúdo de um arquivo
```shell
git diff
```

## Branchs

#### Criar um novo branch

```shell
git switch -c nome-do-branch
```

#### Consultar os branchs existentes
```shell
git branch
```

#### Navegar entre os branchs

```shell
git switch nome-do-branch
```

#### Deletar um branch
```shell
git branch -D nome-do-branch
```


```shell

```

```shell

```

```shell

```

```shell

```

```shell

```
