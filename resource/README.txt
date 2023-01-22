Antes de tudo, crie uma rede na VirtualBox

	Vá em ferramentas > Redes > Nat Networks > Criar > Selecione a que foi criada > modifique o nome para lab

https://www.kali.org

DOWNLOAD & IMPORTAÇÃO na Virtual Box

	Site > Donwload > Virtual Machine > Opções 64-bit ou 32-bit, das plataformas VMware e Virtual box (64-bit + VirtualBox) > Download

descompacte o arquivo que foi feito o download

	Abra o VM > Novo > De um nome
		escolha a pasta onde a máquina virtual ficará
		escolha o tipo: linux
		versão: debian 64-bit 
	> próximo, configure a memória RAM > próximo, disco rígido
		utilizar um disco virtual existente, procurar
		abra o download, a pasta descompactada,
		e escolha o arquivo com a extensão .vdi, clique em abrir
		selecione Kali-Linux...
		clique em escolher
		depois em criar
	> agora com a máquina já criada > vá em configurações > rede conectado: NAT nome: lab > salve e feche as configurações > agora já pode ser aberto

ALTERAÇÃO DE SENHA PADRÃO

por padrão, usuário e senha: kali

para alterar: abra o terminal

CONFIGURAÇÃO DE TECLADO
	
procure por keyboard na barra de pesquisa
	abra a ferramenta > Layoyt > desative as configurações padrão (Use System defaults) > add(adicionar)

	sudo setxkbmap -model abnt2 -layout br