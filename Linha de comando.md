## Baseado no sistema Kali Linux

user@host - usuário e host

## ATALHOS

* limpeza
	* `ctrl + l`: limpa a área, mas os comandos já feitos continuam a existir em cima, sem aparecer até arrastar

* abrir
	* `ctrl + shift + t`: nova aba de comando
	* `ctrl + alt + t`: nova guia de comando

* terminator - terminal instalado
	* `ctrl + shift + o`: divisão em baixo
	* `ctrl + shift + e`: divisão lateral
	* `ctrl + shift + d`: fecha a divisão selecionada, ou a última feita

* alterar entre usuário/sessões
	* `ctrl + alt f`'número': altera entre sessões

* cancelar e suspender
	* `ctrl + c`: cancela a atividade
	* `ctrl + z`: suspende a atividade

<hr>

## OPERADORES

* `<>` - redirecionamento
* `|` - piping, canalizar a saida de um comando para outro comando
	ex: ler um arquivo e passar a saida que seria mostrada para outro comando

	* `>` substitui algo dentro de um arquivo
		* `echo "msg" > saida.txt`
	* `>>` adiciona algo dentro de um arquivo
		* `echo "msg" >> saida.txt`
	* `2>` susbtitui o conteúdo anterior para a "resposta" do comando atual, para dentro do arquivo
		* `cat arqinexistente.txt 2> saida.txt`
	* `2>>` adiciona a "resposta" de um comando para dentro de um arquivo
		* `cat arqinexistente.txt 2>> saida.txt`
	* `|` canalizar a saida de um comando
		* `cat saida.txt | wc -m`
	* `| >` canalizar e substituir
		* `cat saida.txt | wc -m > saida.txt`

<hr>

## COMANDOS
### básicos / principais

* `clear` - limpar
* `*` englobar

<hr>

### modificação/manipulação
* **ECHO**
	* echo - exibir uma linha de texto	
		* `echo "Hello World!"`
		
	* echo + operador >
		* `echo "msg" > nome-arquivo` - escreve e subtitui (>) o conteudo do arquivo
		* `echo "msg" >> nome-arquivo` - escreve e adiciona (>>) a mensagem no arquivo
	* echo + operador |
		`echo "Olá novo mundo" | sed 's/Novo/Velho/'` - a palavra novo sera substituida pela palavra velho
		`echo "Olá novo mundo" | cut -f 2 -d " "`
			`-f 2` - campo 2
			`-d " "` - delimitador
			`*` - vai exibir apenas 'novo'

	* echo $nomevar - mostra o que tem dentro de uma variável
		`echo $SHELL` - mostra qual shell você está usando no momento

* **TOUCH**
	* touch: criar um arquivo
		`touch nome-do-arquivo`

* **MKDIR**
	* mkdir: criar uma pasta
		* `mkdir nome-pasta`

* **NANO**
	* nano: abre um arquivo e dá a possibilidade de modificalo
		* `nano nome-arquivo`

* **RM**
	* rm: remover arquivos ou diretórios
		* `rm nome-arquivo`
		* `rm diretório`
		* `rm *` - deleta tudo que term no diretório
		* `rm letras-presentes-no-nome*` - deleta tudo que tiver a sequência de letras especificada
			* `rm ol*`	

* **MV**
	* mv: mover um arquivo ou diretório para outro diretório
		* `mv nome-arquivo diretório`

* **CP**
	* cp: copia um arquivo ou diretório para outro diretório
		* `cp nome-arquivo diretório`
	
* **CUT**
	* cut: remover seções de cada linha de arquivos
		* `cut -d "ex:espaço" -f "qual campo"`
		* `cut -d " " -f5`

* **LN**
	* ln: fazer links entre arquivos - links simbólicos
		`ln -s caminho arquivo-nome`
<hr>

### encontrar/listar/descobrir
* **LS** 
	* `ls`: lista todos os arquivos de um diretório
		* `-l` - usa formato de lista longa para mostrar os arquivos, e mostra algumas informações como [permissões] e [usuário]
		* `-a` - mostra todos os arquivos, até os ocultos (.)
		* `-B` - não lista entradas que terminem com ~
		* `-h` - mostra os tamanhos como 1KB, 1M e 1G etc...
		* `-H` - segue os links simbólicos listados na linha de comando
	* combinações
		* `-la` - lista todos os arquivos com informações em formato de lista longa
		
* **GREP**
	* grep: exibir apenas linhas, plavras... que contenham certar palavras
		* `grep feb`
		* `grep -i feb`
			`-i` - ignora letras maiúsculas e minúsculas
	
* **FIND** 
	* find: procurar arquivos
		* `find / -name "nome-arquivo"` - por nome
			* `/` : caminho
			* `-user` - por usuário
			* `-atime` - por tempo = +1(mais de um dia) -1(menos de um dia)
			* `-empty` - vazios
			* `-perm 'soma ex: perm=777'` pela permissão
	
* **LOCATE**
	* locate: localizar arquivo especifico
		* `locate nome-aquivo`

* **FILE**
	* file: mostra o tipo/formato de uma arquivo
		* `file nome-arquivo`

* **WHEREIS**
	* whereis: mostra o caminho em que o arquivo se encontra
		* `whereis nome-arquivos`
			
<hr>

### ler
* **WC**
	* wc: exibir contagens de nova linha, palavra e byte para cada arquivo
		* `-l` - exibir quantidade de linhas de um arquivo
			`wc -l nome-arquivo`
		* `-m` - exibir quantos caracteres tem no arquivo
			`wc -m nome-arquivo`

* **CAT**
	* cat: exibe o que tem no arquivo, sem entrar
		`cat nome-arquivo`

* **HEAD**
	* head -n: mostra a quantidade de linhas pedidas, de cima para baixo
		* `head -n2 nome-arquivo`		

* **TAIL**
	* tail -n: mostra a quantidade de linhas pedidas, de baixo para cima
		* `tail -n4 nome-arquivo`
		* `tail -f nome-arquivo` - monitora o arquivo em tempo real

<>

### navegar 
* **PWD**
	* pwd: mostra o caminho em que você se encotra
		* `pwd`

* **CD** 
	* cd: avança ou retrocede um diretório
		* `cd Desktop/` : avançar
		* `cd ..` : pasta anterior
		* `cd -` : diretório anterior

<hr>

### downloads
* **WGET**
	* wget: download
		* `wget -O nome-arquivo URL`
			* `-O` - para nomear o aquivo que será feito o download
			* `nome-arquivo` - nome dado ao arquivo
			* `URL` - link para baixar

* **CURL**
	* curl: ferramenta para transferir dados para um servidor ou de um servidos com alguns protocolos (HTTPS, FTP, FTPS, IMAP...) - downloads ou uploads
		* `curl -o nome-arquivo URL`
			* `-o` - para nomear o aquivo
			* `nome-aquivo` nome dado
			* `URL` link para baixar
		* `curl URL > index.html`
			* `download do link > enviado para o aquivo index.html` - download página

* **AXEL**
	* axel - acelerador de downloads
		* `axel -a -n 20 -o nome-arquivo URL`
			* `-a` - barra de progresso
			* `-n` - número de conexões para fazer o donwload
			* `-o` - nomear o arquivo
			
<hr>

### atualização/intalação/remoção
* **APT UPDATE**
	* `apt update`: verificar atualizações

* **APT LIST --UPGRADABLE**
	* `apt list --upgradable` - verificar lista de pacotes que podem ser atualizados

* **APT UPGRADE** 
	* `apt upgrade` - atualizar pacotes
		* `sudo apt upgrade`

* **APT-CACHE** 
	* apt-cache search: exibe informações armazenadas no banco de dados do cache
		* `apt-cache search terminator`
	
* **APT INSTALL**
	* apt install: instalar
		* `sudo apt install pacote`
			* `sudo apt install terminator`
			* `sudo` - executar um comando como outro usuário
	
* **DPKG** 
	* dpkg: instalar .deb
		* `sudo dpkg -i nome-pacote.deb`

* **APT REMOVE**
	* apt remove: desinstalar
		* `sudo apt remove nome-pacote` - desinstala deixando rastros
		* `sudo apt remove --purge nome-pacote` - desinstala completamente, apagando todos os dados
		* `sudo apt remove --purge 'nome completo do arquivo'` - desinstalar .deb

<hr>

### compactar e descompactar
* **-CF**
	* rar, tar, 7z: compactar
		* `tar -cf nome-arquivo-a-compactar.tar nome-aquivo1 nome-arquivo2`
			`tar` - extensão
			`-cf` - ação
			`nome-aquivo-a-compactar` - nome final, do arquivo compactado
			`nome-arquivo1 e 2` - conteúdo do arquivo compactado
			
* **-XF** 
	* rar, tar, 7z: descompactar
		* `tar -xf nome-arquivo-compactado.tar`
			* `tar` - extensão
			* `-xf` - ação
			* `nome-arquivo-compactado` - arquivo que será descompactado
			
* **UNZIP**
	* unzip: descompactar
		* `unzip arquivo.zip`

<hr>
	
### ajuda
* **MAN** 
	* man: abre o manual do comando, com todas as variações e informações
		* `man ls`

* **--HELP**
		* --help: exibe as informações do comando
			* `ls --help`
			
<hr>

### usuário/permissões (PARA MAIS INFORMAÇÕES, IR EM PERMISSOES.TXT)
* **WHOAMI**
	whoami: mostrará o nome do usuário atual
	
* **SU**
	* su: trocar de usuário
		* `su nome-usuário`
    	* exit: sair do usuário

* **CHMOD**
	* chmod: setar permissões
		* `sudo chmod 'letra q representa o usuário'='permissões desejadas' nome-arquivo`
			* `sudo chmod u=rwx, g=---, o=--- nome-arquivo`

<hr>

### ver processos/gerenciador de tarefas (PARA MAIS INFORMAÇÕES, IR EM PROCESSOS.TXT)

* **HTOP**
	`htop` - mostra de forma colorida e demarcada, vizualização faculitada

* **TOP**
	* `top` - mostra de forma seca, vizualização confusa

<hr>

### variáveis e alias 
* **ENV**
	* `env` - mostra todas as variáveis sendo executadas

* **NOMEVAR**
	* NOMEVAR: criar variável
		* `NOMEVAR="conteúdo"`

<hr>

### comparação de arquivos
* **COMM**
	* comm: compara 2 ou mais arquivos com uma visualização complicada, em colunas
		* `comm arq1 arq2`
		* colunas
			* 1ª: informações exclusivos do arq1
			* 2ª: informações exclusivos do arq2

* **VIMDIFF** 
	* vimdiff: compara 2 ou mais arquivos com uma visualização boa, bem demarcada e também em colunas
		* `vimdiff arq1 arq2`

<hr>

### monitoramento
* **W**
	`w` - mostra informações dos usuários que estão conectados

* **WATCH**
	* watch: executar um programa periodicamente, mostrando a saída em tela cheia
		* `watch -n0.2 w`
			* `-n` - tempo para repetir certo comando
			* `0.2` - 2 segundos
			* `w` - comando a ser repetido

<hr>

### gerenciamento
* **JOBS** 
	* `jobs` - verifica tarefas em andamento

* **BG %1**
	* `bg %1` - executar tarefas em segundo plano, retoma em 2º plano uma atividade suspensa

* **FG %1**
	* `fg %1` - retomar tarefa em segundo plano para primeiro plano

* **&**
	* `&` - ao colocar & ao fim de um comando, ele fica sendo executado em segundo plano
		* `ping -c 500 localhost > ping.txt &`

* **SIGTERM** - mata o processo, mas permite uma limpeza
* **SIGKILL** - matar o processo - não faz uma limpeza do que já foi feito
* **SIGSTOP** - parar/suspender processo

* **SYSTEMCTL** 
	* `systemctl [option] [service]` 
	* opções:
		* `start` - iniciar
		* `stop` - parar
		* `enable` - ativar
		* `disable` - desativar

<hr>

### executar
* **SCRIPT**
	* ./nome-arquivo.extensão
	* ./function.js
