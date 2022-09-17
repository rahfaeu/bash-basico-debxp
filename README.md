# 🦊 Curso Básico de Programação em Bash (DEBXP)
Aqui temos todo o conteúdo do curso que realizei através da página: https://debxp.org/

## Table of Contents

- [Aula 1 - Conceitos Básicos](#aula-1-conceitos-basicos)
  - [1.1 - Revendo o terminal do Linux](#1-1-revendo-o-terminal-do-linux)
  - [1.2 - O prompt da linha de comando](#1-2-O-prompt-da-linha-de-comando)
  - [1.3 - Tipos de shell](#1-3-tipos-de-shell)
  - [1.4 - O que é o Bash](#1-4-o-que-e-o-bash)





## Aula 1 - Conceitos Básicos

### 1.1 - Revendo o terminal do Linux

Mesmo que você nunca tenha escrito um script, se você ja usou o terminal
do Linux, você já utilizou o shell!

O shell é uma camada do sistema operacional
responsável por fazer uma interface entre o usuário e o kernel.

HARDWARE <---> [ KERNEL | SHELL ] <---> USUÁRIO
	       SISTEMA OPERACIONAL  ^
                                    |
	    Via terminal/console ---+

* O shell é um interpretador de comandos.

* Esses comandos podem vir de entrada padrão (terminal) 
  ou de um arquivo (script).

Além de permitir a execução de comandos, o shell possui
os mesmos recursos de qualquer linguagem de programação
de alto nível, como:

* Manipulação de variáveis
* Estrutura de controle de fluxo
* Laços de repetição (loops), etc...

Essa característica é o que nos permite criar scripts, 
automatizar tarefas e criar programas para as mais 
diversas finalidades.

### 1.2 - O prompt da linha de comando

Quando iniciado, o shell procura suas configurações
globais, as configurações do usuário e, finalmente, 
exibe um indicador chamado "prompt de comando", 
que é onde o usuário irá digitar seus comandos.

Prompt típico do Debian GNU/Linux:

usuario@hostname:~/caminho$

Mas aqui nós utilizaremos o prompt assim...

:~$ - para comandos executados como usuário normal.
:~# - para comandos executados como usuário "root".

### 1.3 - Tipos de shell

Existem vários tipos de shell, entre eles...

* sh	- Bourne Shell
* bash	- Bourne Again Shell
* rbash	- Restricted Bash
* dash	- O shell padrão do BSD
* zsh 	- (z-shell) Zero Shell
* fish	- Friendly Interactive Shell

### 1.4 - O que é o Bash [top](#table-of-contents)

O bash, ou Bourne Again Shell é uma implementação aprimorada do inter
