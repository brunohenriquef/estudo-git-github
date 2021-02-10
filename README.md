# Um estudo de Git e GitHub

**Este é um estudo público de Git e GitHub feito por mim (Bruno). Caso haja erros de ortografia ou informações erradas por favor me avise.**

---
---

# História Git e GitHub

* Em 1985 nascia **CVS** (*Concurrent Versions System*), uma famosa ferramenta de versionamento. 
   * Centralizado (precisava de conexão direta com o repositório central para funcionar)
   * Open Source
   * Popular
   * Havia problemas

* Nos anos 2000 surgia o SVN (*Subversion*), outra ferramenta de versionamento
   * Centralizado
   * Open Source
   * Em atividade até os dias atuais
   * CVS-like

* No mesmo ano surgia o BitKeeper, com uma proposta diferente. O conhecido até então sistema distribuído, em que cada pessoa possui uma cópia local do repositório principal
   * Distribuído
   * Inicialmente pago, mas com a chegada da versão *community* logo depois
   * Não era parecido com nenhum dos anteriores
   * **Linux era hospedado aqui** (importante)

**Inicio da briga:**

* Em 2004, Andrew Tridgell utilizou engenharia reversa no BitKeeper e "destravou" metadados indisponíveis na versão community, criando assim o *SourcePuller*
* Larry McVoy (criador do BitKeeper) não gostou disso e começou as disputas com Tridgell. 
* Em 2005, o BitKeeper anunciou sua nova licença, proibindo muitos dados importantes para os desenvolvedores, deixando isto apenas na versão comprável do programa.
* Linus Torvalds (criador do Linux, que utilizava o BitKeeper) ficou *P I S T O L A* com isso e resolveu criar seu próprio software de versionamento
* E no mesmo ano de 2005 surgia a ferramenta deste guia de estudos, o Git.
   * Distribuido
   * Open Source
   * Feito em poucos dias e com qualidade
   * Focado em performance 

* **Em 2008 surgia o GitHub**
   * Pago (mas com mente aberta, diferente do carinha da outra ferramenta de versionamento ai de cima )
   * Hospedagem de códigos com Git
   * Em 2018 foi comprado pela *Microsoft*
   * 2020 GitHub comprou a *NPM* (Node Package Manager)

*Curiosidade: Em 2018 o GitHub levou o maior ataque DDoS da **história**, com conexões de **1.35 TB/s***

---
---

# Instalando Git

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

---
---

# Configurando Git

**Todo comando do Git começa com (literalmente) a palavra `git`**

* Primeiro precisamos configurar nosso nome de usuário e de e-mail. Para isso usamos o comando:
   * `git config --global user.name` e `git config --global user.email`
   
* Passando logo depois disto o valor entre aspas duplas:
   * `git config --global user.name "Bruno"`

---
*Para acessar uma informação salva só precisa digitar novamente o comando, mas desta vez não passando nenhum valor, desta forma ele retornará o dado.*


*A parte `config` como o próprio nome ja diz, acessa as ferramentas de configuração do Git. Logo em seguida definimos `--global`, que englobará todos os repositórios da sua máquina*

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

# 


