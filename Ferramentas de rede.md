## Ferramentas de rede

* PING
	* `ping <target>` - verifica o endereço do alvo
		* `-4` - verifica apenas o endereço ipv4
		* `-i` - muda o tempo de intervalo entre as solicitações de ping
		* `-v` - permite uma saida mais detalhada, verbose

* TRACEROUTE
	* `traceroute <destination>` - mapea o caminho de uma solicitação até seu destino
		* `-i` - especificar a interfaco ao utilizar o traceroute
		* `-T` - usar solicitações TCP SYN ao rastrear uma rota

* DIG
	* `dig <domain> @<dns-server-ip>` - consultar manualmente os servidores dns recursivos escolhidos, para obter informações sobre um dominio
