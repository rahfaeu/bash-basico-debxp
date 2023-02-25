# 🦊 Curso Básico de Programação em Bash (DEBXP)
Aqui temos todo o conteúdo do curso que realizei através da página: https://debxp.org/

Playlist do Curso: [Curso Básico de Programação em Bash](https://debxp.org/cbpb/)
O curso é apresentado pelo **Brau Araujo** e você pode apoiar ele pelos links abaixo:

- [Apoio mensal no Apoia.se](https://apoia.se/debxpcursos)
- [Doação pelo PicPay](https://app.picpay.com/user/blauaraujo)
- PIX: pix@blauaraujo.com

## Table of Contents

- Aula 1 [Conceitos Básicos](#conceitos-basicos)
  - 1.1 [Revendo o terminal do Linux](#revendo-o-terminal-do-linux)
  - 1.2 [O prompt da linha de comando](#o-prompt-da-linha-de-comando)
  - 1.3 [Tipos de shell](#tipos-de-shell)
  - 1.4 [O que é o Bash](#o-que-e-o-bash)
  - 1.5 [Os comandos "built-ins" do Bash](#os-comandos-built-ins-do-bash)
  - 1.6 [O terminal como console interativo](#o-terminal-como-console-interativo)
  - 1.7 [Qual Shell estamos utilizando](#qual-shell-estamos-utilizando)
- Aula 2 [Antes do primeiro script](#antes-do-primeiro-script)
  - 2.1 [Revisão Aula 1](#revisao-aula-1)
  - 2.2 [Comando test ([ ] / [[ ]])](#comando-test)

## Conceitos Básicos

### Revendo o terminal do Linux

Mesmo que você nunca tenha escrito um script, se você ja usou o terminal do Linux, você já utilizou o shell!

O shell é uma camada do sistema operacional responsável por fazer uma interface entre o usuário e o kernel.

HARDWARE <---> [ KERNEL | SHELL ] <---> USUÁRIO
	       SISTEMA OPERACIONAL  ^
                                    |
	    Via terminal/console ---+

* O shell é um interpretador de comandos.

* Esses comandos podem vir de entrada padrão (terminal) ou de um arquivo (script).

Além de permitir a execução de comandos, o shell possui os mesmos recursos de qualquer linguagem de programação de alto nível, como:

* Manipulação de variáveis
* Estrutura de controle de fluxo
* Laços de repetição (loops), etc...

Essa característica é o que nos permite criar scripts, automatizar tarefas e criar programas para as mais diversas finalidades.

### O prompt da linha de comando

Quando iniciado, o shell procura suas configurações globais, as configurações do usuário e, finalmente, exibe um indicador chamado "prompt de comando", que é onde o usuário irá digitar seus comandos.

Prompt típico do Debian GNU/Linux:

```sh
usuario@hostname:~/caminho$
```

Mas aqui nós utilizaremos o prompt assim...

`:~$` - para comandos executados como usuário normal.
`:~#` - para comandos executados como usuário "root".

### Tipos de shell

Existem vários tipos de shell, entre eles...

* sh	  - Bourne Shell
* bash	- Bourne Again Shell
* rbash	- Restricted Bash
* dash	- O shell padrão do BSD
* zsh 	- (z-shell) Zero Shell
* fish	- Friendly Interactive Shell

### O que é o Bash
[top](#table-of-contents)

O bash, ou Bourne Again Shell é uma implementação aprimorada do interpretador de comandos Bourne Shell (sh) que apresenta todos os recursos e características de uma linguagem de programação de alto nível.

Por configuração, o bash pode ser compatível com os padrões POSIX, possibilitanto que seus scripts sejam executados em diversos sistemas "unix like" sem alterações.

POSIX: São normas para manter a compatibilidade.

Desenvolvido originalmente por Brian Fox e continuado por Chat Ramey, o bash foi lançado em 1989 como um Software Livre.

O bash é o shell padrão do Projeto GNU e da maioria das distribuições Linux.

### Os comandos "built-ins" do Bash
[top](#table-of-contents)

Os comandos "built-ins" são os "comandos internos" do bash.

Para ver a lista completa dos comandos built-ins, podemos executar o seguinte comando:

```sh 
help
```

Notamos que nem todo comando do terminal é um built-in do shell!

Se o retorno do comando acima for um erro, significa que o comando não é interno do shell, Por exemplo...

```sh 
help ls
```

Outra forma de descobrir se um comando é interno, é só executar:

```sh 
type <nome_do_comando>
```

Alguns exemplos:

```sh 
type cd
```
Retorno: `cd é um comando interno do shell`

O comando type exibe informação sobre o tipo de comando.
Para cada NOME, indica como ele seria interpretado se fosse usado como um nome de comando.

### O terminal como console interativo
[top](#table-of-contents)

* Muitas linguagens oferecem consoles interativos onde você pode testar e executar trechos do seu programa.

* No nosso caso, o emulador de terminal também pode ser visto como o console interativo do bash/shell.

* Para nós, é importante que ele seja visto dessa forma a partir de agora!

* O terminal será, daqui pra frente, a nossa principal ferramenta de trabalho e nosso melhor amigo!


### Qual Shell estamos utilizando 
[top](#table-of-contents)

Existem duas formas simples de descobrir qual shell está sendo utilizado no nosso sistema:

Método 1: comando `echo $0`
A variável '0' representa a aplicação que está sendo executada.

```sh 
echo $0
```

Método 2: comando `echo $SHELL`
 
```sh 
echo $SHELL
```

## Antes do primeiro script

### Revisão Aula 1
[top](#table-of-contents)

1. Aprendemos que um script é um arquivo de texto contendo comandos que normalmente digitamos no terminal.
2. Aprendemos também que o shell é um interpretador que executa comandos que podem vir da entrada padrão (terminal), ou de um arquivo (script).

- Quando trabalhamos digitando os comandos no terminal, estamos utilizando o shell de forma `interativa`.
- Quando escrevemos os comandos em arquivos (scripts), estamos utilizando o shel de forma `não interativa`.

Umas das utilidades dos scripts, é a possibilidade de executar comandos "em lote", em vez de digitar um por um no terminal.

Poderíamos criar um arquivo chamado `infos.sh` e dentro dele incluir os seguintes comandos:

```sh
#!/bin/bash

whoami
hostname
uptime -p
uname -rms
```
Para habilitar a execução do script que acabamos de criar, basta executar o seguinte comando no terminal:

```sh
chmod +x infos.sh
```

E para executar o script basta executar:

```sh
./infos.sh
```

### Cuidados e boas-práticas
[top](#table-of-contents)

Nunca saia executando qualquer scrips que encontrar por ai...

- Scripts de terceiros, mesmo que não sejam maliciosos, podem não fazer o que pensamos que fazem.
- Podem ser scripts maliciosos.
- O desenvolver do scrip pode ser inexperiente e a solução dele prejudicar seu sistema.
- Mesmo que o script tenha a solução para o seu problema e que o desenvolvedor seja experiente, a solução dele pode ser incompatível com o seu sistema.

#### Cuidados

Antes de executar qualquer comando ou script, você deve sempre analisar e entender o que ele faz!

#### Boas-práticas

- Organização: Trabalhe criando pastas para organizar seus arquivos dividos assuntos.
- Garanta que seu arquivo de script não tenha um nome de um comando ou aplicativo que já existe no sistema.
- Não salve suas pastas de estudos e testes no caminho do sistema ($PATH).

### Aula 2
[top](#table-of-contents)
#### Comando test ([ ] / [[ ]])

O comando test avalia condições lógicas:

Testando se 10 é menor que 20:

```sh
test 10 -lt 20; echo $?
0
```

Testando se se uma arquivo de script tem permisão de execução:

```sh
> script_file.sh
test -x script_file.sh; echo $?
1
```
No caso acima, o arquivo acabou de ser criado, e por padrão ele é criado sem o permissionamento de execução.

Após atribuir a permissão com o comando `chmod +x`, podemos testar novamente:

```sh
chmod +x script_file.sh
test -x script_file.sh; echo $?
1
```

O comando `test` também pode ser representado por colchetes (`[ ]`), ao invés da palavra `test`, ou até mesmo por colchetes duplos (`[[ ]]`) quando desejar utilizar expressões regulares no testes:

```sh
[ 10 -lt 20 ]; echo $?
0
```

```sh
[[ 10 -lt 20 ]]; echo $?
0
```

> Atenção!<br>
> Não esqueça de considerar os espaços entre os colchetes de abertura e fechamento e seu teste lógico.<br>
> Caso não considere os espaços, um erro irá ocorrer.

```sh
# Correto:
[[ 10 -lt 20 ]]
[ 10 -lt 20 ]

# Errado:
[[10 -lt 20]]
[10 -lt 20]
```