# Git e Github

## Git
### Configurações iniciais 
- Configurando nome de usuário
 
     git config --global user.name "Rui Nascimento"
- Configurando E-mail

    git config --global user.email sruy19@gmail.com
- Visualizando as configurações definidas

    git config --list
- Inicializando um repositório git no diretório

    git init
### Ajuda
- Ajuda sobre os comandos mais básicos

    git help
- Exemplo do comando help, serão mostradas informações sobre o comando add

    git help add
   
### Commit
- Adicionando todos arquivos do repositório

    git add .
- Adicionando um arquivo em específico

    git add <nome_do_arquivo.extensão>
- Adicionando commit, commit seria um ponto na história

    git commit -m "commit initial"
- Quando todos arquvios já estão sendo rastreados, não é necessário usar o add, -a, e podemos juntar o m da mensagem

    git commit -am "comitando"
### Log
- Visualizando os commits, hashs e qual branch foi modificada

    git log
- Visualizando um número específico de commits, nesse exemplo será apresentado os últimos 5 commits

    git log -n 5
- Visualizando commits desde uma data em espećifico, serão exibidos todos commits a partir dessa data

    git log --since=2021-08-17
- Visualizando commits antes de uma data em específico, serão exibidos todos commits antes dessa data

    git log --until=2021-07-16
- Visualizando commits filtrados por um Autor

    git log --author="Nome do Autor"
- Visualizando commits com o grep, filtrando pelos commits, nesse caso ele irá filtrar aquele commit que tiver "initial" na mensagem do commit

    git log --grep="initial"
    
- Visualizando todos commits

    git log --oneline
### Status
- Visualizando o status, isso nos dirá em qual branch estamos, sem há arquivos sem commits

    git status
### Removed 
- Removendo um arquivo para não ser commitado

    git rm --cached nome_arquivo.extensao
### Diff
- Para visualizar as modificações feitas em todos os arquivos

    git diff
- Para ver as diferenças no Stage Area

    git diff --staged
- Verficando as diferenças com letras e cores diferentes

    git diff --color-words
### Rm
- Removendo arquivo do working directory, nesse caso, irá deletar o arquivo

    git rm nome_arquivo.extensão
### Mv
- Renomeando arquivo
    
    git mv nome_arquivo.extensão nome_arquivo2.extensão
- Movendo para outros diretórios

    git mv nome_arquivo.extensao /caminho/diretorio/nome_arquivo.extensão
### Restore
- Restaurando alterações feitas em um arquivo, supondo que você apagou linhas e queira recuperar, ou adicionou linhas e não quer essas linhas novas

    git restore nome_arquivo.extensao
- Restaurando para o working directory e removendo do stage area, caso use o . irá pegar todos arquivos.

    git restore --stateg nome_arquivo.extensao
    
    git restore --staged .
- Alternativa para tirar o arquivo do stage area

    git reset HEAD .
    
    git reset HEAD nome_arquivo.extensão
### --amend
- Modificanda a mensagem do último commit

    git commit --amend -m "msg do commit modificada"
### Checkout
- Como recuperar um arquivo num commit específico

    git checkout inicio_hash -- nome_arquivo.extensão
    
    git checkout e72a2 -- nome_arquivo.md
### Clean
- Removendo arquivos não rastreados, ao fazer isso, ele deleta do working directory,e não há como recuperar na história

    git clean -f
### Revert
- Volta num determinado commit, os arquivos retornam, é importante o trabalho estar todo commitado e sem dependências, o parâmetro X, está relacionado ao número do commit. Exemplo: último committ teria o número 0, penúltimo teria -1, e assim por diante, portando se é -1, colocaremos ~1

    git revert HEAD~X
- Outra alternativa, hash == número do hash do commit em que deseja

    git revert hash
 
### Show
- Apresentandos todas modificações

    git show hash
    
    git show hash --color-words
    
    git show hash -- caminho/diretório/*
    
    git show hash -- caminho/diretório/nome_arquivo.extensão
    
### Gitignore
- Serve para não precisar monitorar arquivos, criar arquivo .gitignore e adicionar o nome dos arquivos que não serão monitorados.

    criar um arquivo .gitignore 
    
    git add .gitignore
    
## GitHub

### Configuração e sincronização
- Após ter um repositório local já configurado e commitado
- Vamos configurar com o repositório no Github, linkando repositório da nuvem com o repositório local

    git remote add origin git@github.com:sruiNascimento/lgeg.git
- Criando a branch main no repo local

    git branch -M main, padrão é master, mudando para main
### Push
- Enviando repo local para a nuvem

    git push -u origin main
- Enviando as modificações para a nuvem

    git push origin main
- Alternativa

    git push
### Pull
- Baixando da nuvem os arquivos mais atuais do mesmo repositório, pois do repositório local está desatualizado e na nuvem está atualizado

    git pull
### Configurando o merge
- Necessário configurar a estratégia padrão

    git config --global pull.rebase false
### Clone
- Fazendo clone de projeto na máquina, o comando irá criar um diretório do repositório da máquina local

    git clone <chave ssh do repo>
 
 - Exemplo
 
     git clone git@github.com:sruiNascimento/GitEGithub.git
