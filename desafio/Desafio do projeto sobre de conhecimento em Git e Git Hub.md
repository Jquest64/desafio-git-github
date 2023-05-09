# Desafio do projeto sobre de conhecimento em Git e Git Hub

## Navegação via command line interface e instalação

### **Via command line**

**Comandos básicos no terminal**

Windows

* cd

* dir

* mkdir

* del/rmdir

Unix

* cd

* ls

* mkdir

* rm -rf

### **Realizando a instalação do Git**

**Passo a passo na instalação no Windows**

* Acessando o site oficial do Git

* Baixar e instalar o Git

* Verificar, se o git bash here e o Git gui here, estão ativados

* Vai dando **next** até o fim da instalação 

 **Passo a passo na instalação no Linux**

* add-apt-repository ppa:git-core/ppa

* apt update

* apt install git

**Verificar a versão do Git** 

ex:

​	git --version

------

## **Entendendo como o Git funciona**
### **Tópicos fundamentais para entender o funcionamento do Git**

* SHA1

* Objetos fundamentais

* Sistema distribuído

* Segurança

SHA (Algoritmo de Hash Seguro) - É um conjunto de funções criptográficas. 

**Exemplo de encriptação.**

​	openssl sha1 *arquivo.txt*

### **Objetos internos do Git**

* Blobs

* Trees

* Commits

**Blobs** - É onde são guardados os arquivos com metadados de tamanho e o tipo do objeto deste arquivo.
**Trees** - Armazenam blobs, vai ser responsável pela montagem da estrutura dos arquivos.
**Commit** - É o objeto que vai juntar tudo. Onde o commit aponta para um tree, que aponta para um parente, ou seja aponta para o último commit, que aponta para o autor, que também aponta para a mensagem.

------

## **Chaves ssh e tokens**

**chave ssh** - É uma forma de comunicação segura encriptada entre duas maquinas.

### **Comandos para criar as chaves**

ex:

​	ssh-keygen -t ed25519 -C [***seul@email.com***](mailto:seuemail@gmail.com)

Vai criar duas chaves que são chamadas de pública e privada, que poderá ser acessada na pasta oculta .ssh.

**Comando para visualizar o conteúdo da chave pública.**
ex:

​	cat id_ed25519.pub

*Copiar o conteúdo da chave para ser usado no site do Git Hub na parte da opção ssh.

**Passando as chaves para o ssh agent.**

ex:

​	eval $(ssh-agent -s)ssh-add id_ed25519

**Clonando um código no Git Hub, copiando o código na aba code no Git Hub na opção SSH e colando o endereço copiado do Git Hub.**

ex:

​	git clone ***colar o endereço copiado***

### **Token de acesso pessoal** 

No Git Hub acesse a opção Developer setting para gerar o token e para clonar o código vai até na aba code na opção **HTTPS**.
**Para clonar o código no repositório local basta colar o endereço.**

ex: 

​	git clone ***colar o endereço copiado***

------

## **Primeiros comandos com Git**

### **Passo a passo**

1. Iniciar o Git Hub
2. Iniciar o versionamento
3. Criar um commit

**Comandos para o repositório local**

* git init

* git add

* git commit

**Criando uma pasta para o repositório local**

ex:

​	mkdir ***livro-receita***

**Iniciando o git na pasta do projeto.**

ex:

​	git init

**Configurando o git da pasta do projeto.**

ex:

​	git config --global user.email **“*seu email*”**

​	git config --global user.name ***nome do usuário***

**Criar um arquivo para o projeto**

ex:

​	bolo.md

**Realizando um commit no projeto.**

ex:

​	git add *

​	git commit -m ***“Coloque uma mensagem para o commit”***

------

## **Ciclo de vida dos arquivo no Git**

### **Passo a passo no ciclo de vida**

**Git Init** - Criando um repositório.

**Untracked** - O git não sabe que tem um arquivo.

**Traked** - O git já sabe que tem um arquivo.

**Unmodified** - Um arquivo que não foi modificado.

**Modified** - Um arquivo que foi modificado.

**Staged** - E onde os arquivos estão se preparando para fazer parte de um outro tipo de agrupamento.

**Commit** - E onde os arquivos vão fazer parte de um commit, ou seja ele envelopa todas as modificações no arquivo. Ele também contém um autor, uma mensagem e uma data.

**O git status** - Vai mostrar se o arquivo está em qual condição do repositório local.

ex:

​	git status

------

## **Introdução ao Git Hub**

**Ver a configuração feita no repositório local.**

ex:

​	git config --list

**Reescrever as configuração feitas no repositório local.**

ex:

​	git config --global --unset user.email 
​	git config --global --unset user.nickname
**Depois escrever novamente a configuração do repositório local.**

ex:

​	git config --global user.email [***seu@email.com***](mailto:seu@email.com)
​	git config --global user.name ***nome do usuário***

Primeiramente, crie um repositório remoto do Git Hub, na opção repositório e depois copie o link do endereço do repositório remoto criado. Marque a opção README, se não tiver o arquivo no repositório local.

**Adicionar à origem, na qual enviar os arquivos para o repositório remoto.**

ex:

​	git remote add origin ***colar o link do endereço do repositório remoto***

**Comando para verificar a lista de repositórios remoto cadastrados.**

ex:

​	git remote -v

**Empurrando os arquivos do repositório local para o repositório remoto.**

ex:

​	git push origin master

------

## **Resolvendo conflitos**

### **Como os conflitos acontecem no Git Hub e como resolvê los**

O conflito surge quando os arquivos são modificados no Git Hub e que são diferentes dos arquivos do repositório local.

**Para resolver o problema do conflito, terá que puxar do repositório remoto e juntar com a versão do repositório local.**

ex:

​	git pull master

**Depois de fazer as modificações nos arquivos puxados, basta adicionar os arquivos para o staged.**

ex:

​	git add*

**Fazendo um commit nos arquivos.ex:git commit -m “resolve conflitos”**
**Empurrando novamente para o repositório remoto.**

ex:

​	git push master
