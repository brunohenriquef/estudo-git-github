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

Versionamento local por si só não resolve muita coisa, para isso precisamos enviar nosso código versionado para algum lugar, e este lugar escolhido é o GitHub (também há outras opções como o Bitbucket, Gitlab, etc).

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

*Curiosidade: Em 2018, o GitHub levou o maior ataque DDoS da **história**, com conexões de **1.35 TB/s***

---



# Instalando Git

* ***Antes de instalar o Git, recomendo instalar o Visual Studio Code da Microsoft. Esse editor nos permitirá ter uma ótima integração com o Git e nos fornecerá ajuda visual para certas questões***

[Clique aqui para baixar o Git](https://git-scm.com/)

* *A fase de instalação é tranquila e intuitiva*.
* *Caso não saiba de algo apenas ignore, você poderá rodar o instalador novamente e mudar estas opções*.

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
* Configurando opções experimentais

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



---

# Iniciando um projeto e primeiro commit

* Para iniciar um novo projeto (repositório) Git é necessário acessar a pasta dos arquivos que você deseja pelo terminal e digitar o seguinte comando:
   * `git init`

* Com isso, o git irá criar um novo repositório e já irá inicializá-lo na pasta selecionada.
   * Se na pasta em questão já houver um repositório git criado ele irá reinicializar o projeto.

* **Importante: Quando iniciamos um repositório Git, no diretório selecionado é criado uma pasta oculta chamada `.git`, nela é onde tudo fica salvo. Você pode acessá-la ativando as pastas ocultas de seu sistema operacional. Se excluirmos a pasta perdemos todo o histórico de nosso projeto, então cuidado.**

* Feito o passo, o Git já estará pronto para ser usado.

* Agora abra seu editor de texto na pasta selecionada e comece a trabalhar.
   * Quando achar que já fez o bastante e gostaria de salvar o estado daquele projeto, abra novamente o terminal.

* Para ver em que estava mexendo, digite: `git status` 
   * Você pode perceber que os arquivos aparecerão em vermelho. Primeiramente os arquivos estarão como *untracked*, ou seja, o git não está monitorando as mudanças nestes arquivos. Para resolver este problema temos que *rastreá-los* (*tracked* files), utilizando o comando `git add nomeDoArquivo` (note que você só tera que rastreá-los uma única vez, após isso o Git estará detectando mudanças no arquivo). Depois disto, todas as mudanças continuarão aparecendo em vermelho, com a diferença que agora ele está detectando as mudanças feitas e não se o arquivo é novo ou não.

* Para salvarmos a versão do projeto, faremos algo que se chama **commit**. Fazendo um commit, o Git criará um ponto na história, que poderemos voltar mais adiante.
   * Antes de fazermos o commit, precisamos indicar ao Git quais arquivos queremos que estejam incluídos nesse ponto da história. Para indicar quais arquivos devemos salvar, é o mesmo comando mostrado acima, digite:
      * `git add nomeDoArquivo` ou se preferir adicionar todos os arquivos troque o nome do arquivo por um ponto `.`.
      * Se você já rastreou um arquivo e não fez alterações nele não precisará adicioná-lo duas vezes.
      * Quando rodamos o comando, colocamos todos os arquivos selecionados em modo de **Staged** (está pronto para ser "commitado").

* Agora, tudo que precisamos é literalmente fazer o commit, e para isso usa-se o seguinte comando:

   * `git commit -m "Deixe uma mensagem sobre o que é seu commit"`
      * O `-m` indica que iremos deixar uma mensagem, que é sobre quais mudanças você fez no código. Seja simples e direto.

* **Ao invés do `-m`, podemos utilizar o `-am`. Com isso, o git irá automaticamente adicionar todos os arquivos modificados no estado *Staged* e fazer o commit, tudo de uma vez (não se esqueça de deixar a mensagem).**


* Neste momento já temos nosso primeiro ponto na história do projeto.

* Para ver seus commits já feitos utilize o comando: 
   * `git log`
      * Notará as datas, a chave do commit, a mensagem, o autor e o e-mail de quem fez.

* Repita o processo quantas vezes achar necessário.

* Aprenderemos como voltar versões um pouco mais adiante

---

# Enviando seu projeto para o GitHub

* Agora que aprendemos a fazer o versionamento local, e você já tem uma versão inicial de seu projeto, estamos prontos para enviá-lo para o repositório remoto (GitHub).

* Vá para seu GitHub e crie um repositório

* O próximo passo é o seguinte:

   * Precisamos adicionar ao nosso Git o local onde devemos enviar nosso código. E para isso usamos o comando:

      * `git remote add origin URLdoRepositórioNoGitHub`
      
         * Com isso já definimos o local. O **origin** nada mais é que um nome abreviado para quando formos enviar o código utilizarmos ele, mas poderia ser qualquer outro nome (origin é o padrão).

         * Dica: conseguimos ver todos nossos repositórios remotos com o comando `git remote -v`
   
   * Agora temos que fazer um **push** (que nada mais é do que literalmente enviar os códigos para o repositório remoto). 
      * Utilizamos o seguinte comando: 

         * `git push origin`
            * Neste simples comando acabamos de enviar o nosso código.

   * Espere!

      * Quase esquecemos de uma preciosa parte! Você já deve ter notado que a seguinte mensagem apareceu:

         * ```fatal: The current branch master has no upstream branch. To push the current branch and set the remote as upstream, use git push --set-upstream origin master ```
         
         * Ele está nos dizendo que precisamos definir nossa **branch** principal (veremos isso mais tarde). 
         
         * Podemos ignorar isto por enquanto apenas digitando o que ele pediu:

            * `git push --set-upstream origin master` 
               * Ou então uma versão mais curta `git push -u origin master`
      
      * Este tipo de mensagem não aparecerá tão cedo até mexermos com branchs

      * Então, para dar push apenas utilize o comando mostrado um pouco mais acima `git push origin`

      * Ele irá pedir seu nome de usuário GitHub e senha, coloque.
         * *Dica*: há algo no Git chamado Credential Helper, eu particularmente não uso e NÃO recomendo, pois já tive problemas DEMAIS com isso. Como o nome diz, ele salva seus dados para que não precise ficar repetindo a ação de colocar senha e usuário.


* Agora que já subimos nosso código você pode ir lá conferir.

   * Acesse seu GitHub e vá em seus repositórios, clique no selecionado e verá todos seus arquivos lá dentro.

---

# Arquivo README e Licenças

* Todo bom repositório que se preze possui instruções de como usar o projeto. Para isso adicionamos um arquivo chamado README, de extensão .md (extensão para linguagem Markdown).

* Aliás, este estudo que está lendo foi feito todo na área README :)

* O que é a linguagem *Markdown*?

   * É uma linguagem de marcação, igual o HTML é.
   * As vantagens do Markdown são: 
      * Ele é mais fácil de aprender e usar, também é mais fácil a leitura do código.

* Crie em sua pasta o arquivo README.md, o GitHub se encarregará de mostrá-lo na primeira página de seu repositório. 

   * Utilize este arquivo para descrever seu código, o que ele faz, como usar e outras informações úteis.
   * Para isso, como eu disse, usamos a linguagem Markdown. Não ensinarei ela aqui pois seria muito complicado, então segue um link de como usar (é simples, eu juro!) [Linguagem Markdown](https://docs.pipz.com/central-de-ajuda/learning-center/guia-basico-de-markdown#open)


* **Licença**

   * Além do README, todo bom repositório possui uma licença de uso.

   * É com ela que diremos a quem visitar nosso perfil o que podem ou não fazer com o que desenvolvemos.

      * Utilizaremos licenças prontas que o próprio GitHub nos oferece:

         * Vá para seu repositório no GitHub e entre nele
         * Crie um novo arquivo (no próprio GitHub, não em sua máquina)
         * Nomeie ele de LICENSE (exatamente assim)
         * Logo ao lado aparecerá a opção **Choose a license template**
         * Em seguida, escolha um tipo de licença (claro, você terá que ler todas elas para entender)
         * Após isso, clique em Review and submit

      * Eu encorajo a todos que em seus projetos de fins não monetários, utilize a licença MIT (leia a licença). 
      * Assim ajudaremos nossa comunidade e incentivaremos mais pessoas a fazerem isso.

---
---

# Voltando no tempo

* Como eu disse, a possibilidade de restaurar versões de arquivos é algo poderosíssimo, e para isso, vamos realizar os seguintes passos:

* Antes de voltar no tempo, você pode ver as alterações que fez nos arquivos com o comando `git diff` para visualizar todos, ou `git diff nomeDoArquivo`.
   * Ou então, se estiver usando o Visual Studio Code, nos ícones da esquerda clique em Source Control. Vá até os arquivos modificados, clique com o direito e depois open changes. Desta forma ele abrirá uma nova aba mostrando todas as alterações de uma maneira visual mais agradável do que o terminal.

   * ### Uma forma de fazer isso:

   * Primeiramente digite `git log`, isso irá mostrar todos os commits do projeto.
   * Se você seguiu a dica de ser simples e direto, saberá o que é cada ponto feito na história.
   * Com o ponto escolhido, copie o *hash* (o grande número depois da palavra commit)
      * Mesmo se ainda estiver em dúvida sobre o que foi alterado, utilize o comando `git show numeroDaHash` que ele te mostrará as mudanças dos arquivos.
      * Ou, se preferir, digite `git log --oneline`, e ele encurtará o hash e você pode selecionar apenas aquele número menor.
      * Ou, ainda, se preferir, digite `git log arquivoQueVoceGostariaDeSaber`, e ele mostrará todos os commits envolvendo aquele arquivo em específico.
   * Antes de fazer a operação tenha preferência de que o Git esteja "limpo" (sem nada para commitar, e sem arquivos *staged*).
   * Número copiado, mudanças em mente, hora de reverter:
      * Para reverter, digite o comando `git revert numeroDoHash`, com isso, ele abrirá uma nova página no seu editor de texto mostrando detalhes sobre isso, você pode simplesmente fechar. 
   * Voltando ao terminal e digitando `git log`, verá que agora temos um novo commit, descrito como ***This reverts commit numeroDoHashDoCommitAnterior***
   * Você acabou de voltar no tempo. 

   * ### Uma outra forma:

   * 
---

# Continua!

### Esse estudo está sendo construido aos poucos! Atualizado todos os dias.

---

# Fontes

* Curso de Git e GitHub do professor Gustavo Guanabara [Clique aqui para visualizar](https://www.youtube.com/watch?v=xEKo29OWILE&list=PLHz_AreHm4dm7ZULPAmadvNhH6vk9oNZA)
* Documentação do próprio site do Git [Clique aqui para visualizar](https://git-scm.com/doc)
* Documentação do site do GitHub [Clique aqui para visualizar](https://docs.github.com/)


