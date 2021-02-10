# Um estudo de Git e GitHub

**Este "guia" (que talvez eu mesmo não o considere assim) é mais um material de apoio. Recomendo saber o básico e usar este repositório para uma fonte rápida de consultas. No fim estará algumas fontes das quais tirei as informações com mais precisão.**

**Este é um estudo público de Git e GitHub feito por mim (Bruno), para mim (também Bruno). Caso haja erros de ortografia ou informações erradas por favor me avise.**

---

# O que é um software de versionamento?

## Git é um software de versionamento, isso significa que: 

* É um programa que salva todos as versões e estados de seu projeto, monitorando diferenças feitas nos arquivos.
* Possibilita trabalhar com mais pessoas sem dores de cabeça
* Fácil de resolver conflitos de arquivos
* Oferece segurança e organização

Ao invés de você fazer uma cópia toda vez que achar que aquela versão está boa, apenas digite uns comandos e ficará salvo na história do projeto.

Você poderá voltar no tempo para versões antigas com poucas linhas no terminal, caso faça *coisas erradas* no projeto.

Versionato local por si só não resolve muita coisa, para isso precisamos enviar nosso código versionado para algum lugar, e este lugar escolhido é o GitHub (também há outras opções como o Bitbucket, Gitlab, etc).

---

# GitHub

* O GitHub, um repositório remoto, conta com funcionalidades como:
   * Repositórios ilimitados
   * Possui características de redes sociais
   * Possibilidade de hospedar uma página web simples com GitHub Pages
   * Grande colaboração
   * Dentre muitas outras coisas

---


# História Git e GitHub

* Em 1985 nascia **CVS** (*Concurrent Versions System*), uma famosa ferramenta de versionamento. 
   * Centralizado (precisava de conexão direta com o repositório central para funcionar)
   * Open Source
   * Popular
   * Havia problemas

* Nos anos 2000 surgia o SVN (*Subversion*), outra ferramenta de versionamento.
   * Centralizado
   * Open Source
   * Em atividade até os dias atuais
   * CVS-like

* No mesmo ano surgia o BitKeeper, com uma proposta diferente. O conhecido até então sistema distribuído, em que cada pessoa possui uma cópia local do repositório principal.
   * Distribuído
   * Inicialmente pago, mas com a chegada da versão *community* logo depois
   * Não era parecido com nenhum dos anteriores
   * **Linux era hospedado aqui** (importante)

**Inicio da briga:**

* Em 2004, Andrew Tridgell utilizou engenharia reversa no BitKeeper e "destravou" metadados indisponíveis na versão community, criando assim o *SourcePuller*.
* Larry McVoy (criador do BitKeeper) não gostou disso e começou as disputas com Tridgell. 
* Em 2005, o BitKeeper anunciou sua nova licença, proibindo muitos dados importantes para os desenvolvedores, deixando isto apenas na versão comprável do programa.
* Linus Torvalds (criador do Linux, que utilizava o BitKeeper) ficou *irritado* com isso e resolveu criar seu próprio software de versionamento.
* E no mesmo ano de 2005 surgia a ferramenta deste guia de estudos, o Git.
   * Distribuido
   * Open Source
   * Feito em poucos dias e com qualidade
   * Focado em performance 

* **Em 2008 surgia o GitHub**
   * Pago (mas com mente aberta, diferente do carinha da outra ferramenta de versionamento ai de cima )
   * Hospedagem de códigos com Git
   * Em 2018 foi comprado pela *Microsoft*
   * Já em 2020, o GitHub comprou a *NPM* (Node Package Manager)

*Curiosidade: Em 2018 o GitHub levou o maior ataque DDoS da **história**, com conexões de **1.35 TB/s***

---



# Instalando Git

[Clique aqui para baixar o Git](https://git-scm.com/)

**Na fase de instalação você irá configurar as seguintes coisas:**

* Componentes
* Editor de texto padrão
* Nome da branch principal
* Path
* Usar a biblioteca OpenSSL
* Linhas finais de conversação 
* Emulador do terminal para usar com Git Bash
* Comportamento do Git Pull
* Ajudante de credencial
* Configurando opções extras
* Configurando opçõex experimentais

*Feito isso está concluído*

---

# Configurando Git

* Abra o Git Bash ou seu terminal.

**Todo comando do Git começa com (literalmente) a palavra `git`**

* Primeiro precisamos configurar nosso nome de usuário e de e-mail. Para isso usamos o comando:
   * `git config --global user.name` e `git config --global user.email`
   
* Passando logo depois disto o valor entre aspas duplas:
   * `git config --global user.name "Bruno"`

---
*Para acessar uma informação salva só precisa digitar novamente o comando, mas desta vez não passando nenhum valor, desta forma ele retornará o dado.*


*A parte `config` como o próprio nome ja diz, acessa as ferramentas de configuração do Git. Logo em seguida definimos `--global`, que englobará todos os repositórios da sua máquina.*

---

* Agora configuraremos o nosso editor de texto padrão (caso já tenha definido na instalação esta parte pode ser pulada):
   * `git config --global core.editor "abreviatura do editor ou o caminho dele na sua máquina"`


* Para listarmos todas as configurações do Git podemos usar o comando:
   * `git config --list`


**Adicionando um repositório remoto**

* Para adicionarmos um repositório remoto utilizamos o comando:
   * `git remote add nomeDoRemote URL`
   * E para listar todos os repositórios remotos de seu projeto utilize o comando:
      * `git remote -v`

---

# Iniciando um projeto e primeiro commit

* Para iniciar um novo projeto (repositório) Git é necessário acessar a pasta dos arquivos que você deseja pelo terminal e digitar o seguinte comando:
   * `git init`

* Com isso, o git irá criar um novo repositório e já irá inicializa-lo na pasta selecionada.
   * Se na pasta em questão já houver um repositório git criado ele irá reinicializar o projeto.

* Feito o passo, o Git já estará pronto para ser usado.

* Agora abra seu editor de texto na pasta selecionada e comece a trabalhar.
   * Quando achar que já fez o bastante e gostaria de salvar o estado daquele projeto, abra novamente o terminal.

* Para ver em que estava mexendo, digite: `git status` 
   * Você pode perceber que os arquivos aparecerão em vermelho, isso significa que ele ja detectou mudanças nos arquivos desde a última checagem.

* Para salvarmos a versão do projeto, faremos algo que se chama **commit**. Fazendo um commit, o Git criará um ponto na história, que podemos voltar mais adiante.
   * Antes de fazermos o commit, precisamos indicar ao Git quais arquivos queremos que estejam incluídos nesse ponto da história. Para indicar quais arquivos devemos salvar, digite o comando:
      * `git add nomeDoArquivo`
      * Quando rodamos o comando, colocamos todos os arquivos selecionados em modo de **Staged** (está pronto para ser "commitado")

* Agora, tudo que precisamos é literalmente fazer o commit, e para isso usa-se o seguinte comando:
   * `git commit -m "Deixe uma mensagem sobre o que é seu commit"`
      * O `-m` indica que iremos deixar uma mensagem, que é sobre quais mudanças você fez no código. Seja simples e direto.

* Neste momento já temos nosso primeiro ponto na história do nosso projeto, em que poderemos retorna-lo a qualquer momento.

* Para ver seus commits já feitos utilize o comando: 
   * `git log`
      * Notará as datas, a chave do commit, a mensagem, o autor e o e-mail de quem fez.

* Repita o processo quantas vezes achar necessário.
---

# Fontes

* Curso de Git e GitHub do professor Gustavo Guanabara [Clique aqui para visualizar](https://www.youtube.com/watch?v=xEKo29OWILE&list=PLHz_AreHm4dm7ZULPAmadvNhH6vk9oNZA)
* Documentação do próprio site do Git [Clique aqui para visualizar](https://git-scm.com/doc)
* Documentação do site do GitHub [Clique aqui para visualizar](https://docs.github.com/)


