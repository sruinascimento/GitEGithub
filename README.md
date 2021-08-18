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
