* **R** - read
* **W** - Write
* **X** - execute
* **-** don't have permission
* **T** - sticky bit

<hr>

* leitura(read)
	* `R, 4`
* escrita(write)
	* `W, 2`
* execução(execute)
	* `X, 1`
* especial(sticky bit)
		`T`

<hr>

* diretório
	* `D`
* link
	* `L`
* arquivo 
	* `-` (hífen)

<hr>

* usuário dono - u
	* `r, w, x`
* grupo - g
	* `-, -, x` 
* outros - o
	* `r, w, -`

* **ex:**
	* `-rw-r--r--`
		* `-` - arquivo
		* `rw-` - permissões do adm - U
		* `r--` - grupo de usuários que o arquivo pertence - G
		* `r--` - outros usuários, n são nem donos, nem pertecem ao grupo do arquivo - O
