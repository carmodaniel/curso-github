# Git e GitHub

> ## GIT  
>
>`Sistema com a finalidade de Gerenciar diferentes versões de um documento`

> ## GitHub
>
>`Serviço de WEB compartilhamento para projetos que utilizamo  GIT para verseionamento`

>Link dowload GIT  
[Git - DOWLOAD](https://git-scm.com/downloads)

> ## Comandos configurações Básicas GIT

~~~powershell
# Comando que define o nome do usuário
git config --global user.name "Nome do Usuário"

# Comando define e-mail do usuário
git config --global user.email "usuario@email.com"

# Comado para setar editor padrão no git
git config --global core.editor vscode # informar qual editor será utilizado, no exemplo estou utilizando o VSCODE

# para saber o nome do usuário ou e-mail que está configurado no git:
git config user.name # retorna o nome do usuário

git config user.mail # retorna e-mail do usuário

git config --list # retorna uma lista com todas a configurações do GIT
~~~

## Criando pasta de projeto para o Git

~~~powershell
# Criação da pasta através de comando via terminal, estou utilizando o Windows 11
mkdir git_curso # mkdir cria a pasta conforme o nome escolhido (exemplo pasta git_curso)

# Acessar a pasta do Projeto, utilizando Terminal
cd git_curso

# Depois de acessar o pasta do projeto é necesário executar o comando `git init` esse comando "cria um novo repositório do Git. Ele pode ser usado para converter um projeto existente e não versionado em um repositório do Git ou inicializar um novo repositório vazio."
git init
~~~

## Estados dos arquivos no Git  

Os arquivos no Git sempre se encontram em algum estado: `untracked`, `unmodified`, `modified` e `stage`. Entender esses estados nos ajuda a saber melhor qual o momento certo de usar cada comando.

## Untracked
>
>Arquivos marcados como untracked são arquivos não monitorados pelo Git. Os arquivos que acabaram de ser criados sempre estarão com esse estado. Vamos criar um arquivo chamado arq01 e usar o comando git status para verificar o que ocorreu no repositório.

## Unmodified
>
> Quando realizamos um commit, os arquivos saem de stage para unmodified, isso significa que, na linha do tempo, seu arquivo está igual ao estado salvo no último commit.

## Modified
>
> São os arquivos já monitorados pelo Git que sofreram alguma alteração desde o último commit

## Stage
>
> Os arquivos marcados como stage são os arquivos novos ou modificados que serão salvos no próximo commit. O que o comando anterior git add faz é adicionar os arquivos de untracked e modified para stage

~~~powershell
# O comando git status exibe as condições do diretório de trabalho e da área de staging
# Ele permite que você veja quais alterações foram despreparadas, quais não foram e quais arquivos não estão sendo monitorados pelo Git.
git status
~~~

## Comando git add

~~~powershell
# Adiciona conteúdo” (propor uma mudança qualquer, seja ela alterar, adicionar ou remover um conteúdo) de um arquivo local ao índice ou staging area, que terá a mudança confirmada, posteriormente, com o comando git commit, e finalmente enviada ao repositório remoto pelo git push.
git add # Necessário informar o nome do arquivo 
~~~

## Comando git commit

~~~powershell
# É uma das funções principais do Git. Antes de usar o comando git add é necessário selecionar as alterações que vão ser preparadas para o próximo commit. Então, git commit é usado para criar um instantâneo das alterações preparadas em um cronograma de um histórico de projetos do Git.

git commit -m "" # o -m possibilita escreve um texto para o commit
~~~

## Comando git log

~~~powershell
# O comando git log é a ferramenta básica do Git para explorar o histórico de um repositório. É usado quando se precisa encontrar uma versão específica de um projeto ou saber quais alterações vão ser implantadas por meio do merge de uma ramificação de funções.
git log
git log --decorate # faz com que o git log exiba todas as referências (por exemplo, branches, tags, etc.) que apontam para cada commit.
git log --author="Nome do usuário"  # Para visualizarmos apenas os commits realizados por um autor em específico, podemos utilizar o comando git log --author "Nome do
git shortlog # Exibe os commits por autor e título

git shortlog -sn # Exibe a quantidade de commits por autor
git log --graph # Exibe de forma gráfica  a estrutura de branch do histórico de commits

git show "Necessário incluir a hash"  # O git-show é um utilitário de linha de comando usado para exibir informações expandidas de objetos Git, como blobs, trees, marcações e commits. O git-show tem um comportamento específico por tipo do objeto. As marcações mostram a mensagem da tag e outros objetos incluídos na tag.
# O Git atribui a cada commit um ID exclusivo, denominado SHA ou hash, que identifica: Cada uma das alterações feitas; O momento em que as alterações foram feitas; O autor das alterações

git diff # Exibe todas as diferenças entre sua cópia local e o índice sincronizado

git diff -–name-only # 

git checkout "Nome do arquivo" # Restaura o arquivo da árvore de trabalho

git reset HEAD "Nome do arquivo" # Desfaz alterações locais no estado de um repositório

git reset --soft "Necessário incluir a hash"  # move apenas o ponteiro HEAD para algum outro commit, sem alterar a área de stage ou o diretório de working. É importante notar que, de fato, a operação moverá o branch para o qual o HEAD aponta e, por consequência, moverá também o ponteiro HEAD.

git reset --mixed "Necessário incluir a hash" # Essa opção, além de mover o ponteiro HEAD, faz com que a área de stage contenha o mesmo snapshot do commit para o qual o ponteiro HEAD foi movido, porém não afeta o diretório de working. Por exemplo, imagine que em um repositório foram executados três commits e nenhuma alteração foi feita após o último commit.

git reset --hard "Necessário incluir a hash" # não apenas descarta as alterações na área de stage como também reverte todas as alterações no diretório de working para o estado do commit que foi especificado no comando. Por exemplo, imagine um repositório no mesmo estado dos casos anteriores.
~~~

# GIT Repositório Remoto
A abordagem colaborativa do GitHub para o desenvolvimento depende da publicação de commits do seu repositório local para GitHub para que outras pessoas visualizem, façam buscas e atualizações.
