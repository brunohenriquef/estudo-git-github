# Um estudo de Git e GitHub

**Este é um estudo público de Git e GitHub feito por mim (Bruno). Caso haja erros de ortografia ou informações erradas por favor me avise**
---
## Instalando Git***

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

## Configurando Git***

**Todo comando do Git começa com (literalmente) a palavra `git`**

* Primeiro precisamos configurar nosso nome de usuário e de e-mail. Para isso usamos o código:
`git config --global user.name` e `git config --global user.email`
Passando logo depois disto o valor entre aspas duplas:
`git config --global user.name "Bruno"`

*A parte `config` como o próprio nome ja diz, acessa as ferramentas de configuração do Git. Logo em seguida definimos `--global`, que englobará todos os repositórios da sua máquina*

* Agora configuraremos o nosso editor de texto padrão (caso já tenha definido na instalação esta parte pode ser pulada):
`git config --global core.editor "abreviatura do editor ou o caminho dele na sua máquina"`


* Para listarmos todas as configurações do Git podemos usar o comando:

`git config --list`

