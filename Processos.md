* `PID` - número de identificação
* `USER` - quem é o dono
* `PR` - nível de prioridade
* `NI` -
* `VIRT` - quantida de memoria virtual sendo usada
* `RES` - quantidade de memoria fisica que está sendo usada
* `SHR` - quantidade de memoria sendo compartilhada com outros processos
* `S` - estado em que o processo se encontra
	* `S` = sleeping - aguardando processamento
	* `R` = running - em processamento
	* `T` = traced or stopped - processo parado ou controlado pelo usuário
	* `Z`= zombie - processo em modo zumbi
	* `D` = disk sleep - processo está aguardando para ser gravado em disco
* `%CPU`  - tempo da cpu q foi usado pelo processo
* `%MEM` - porcentagem de memoria fisica usada pelo processo
* `TIME+` - tempo total usado pela cpu para realizar o processo
* `COMMAND` - qual o nome do comando
