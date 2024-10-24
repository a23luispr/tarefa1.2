# Tarefa 1.2 Instalación de zonas mestras primarias en Windows Server



O obxectivo desta tarefa é instalar o servidor DNS  nunha máquina Windows 2019 Server.

Partiremos dunha máquina virtual con Windows 2019 cun único adaptador. Antes de comezar comproba que desde ela se pode acceder a Internet. O nome da máquina debe ser "lukeskywalker" e o enderezo IP 192.168.20.101/24.

Cambiar o nome do equipo:

![imaxe1](/tarefa1_2/imaxes/imaxe1.png)

Cambiar a IP:

![imaxe2](/tarefa1_2/imaxes/imaxe2.png)




Deberás entregar un único documento de Google Drive onde pegues o resultado de cada unha das tarefas.


1. Instala o servidor DNS no equipo lukeskywalker. Comproba que xa funciona coma servidor DNS caché pegando no documento de entrega a saída deste comando  nslookup -norecurse www.starwars.com localhost

Instalamos o servidor DNS:
![imaxe3](/tarefa1_2/imaxes/imaxe3.png)

![imaxe4](/tarefa1_2/imaxes/imaxe4.png)

2. Configura o servidor DNS para que empregue como reenviador 8.8.8.8. pegando no documento de entrega a captura de pantalla da configuración do reenviador e a saída deste comando: nslookup -recurse www.starwars.com localhost

![imaxe5](/tarefa1_2/imaxes/imaxe5.png)

![imaxe6](/tarefa1_2/imaxes/imaxe6.png)


3. Instala unha zona primaria de resolución directa chamada "academia.jedi" e engade os seguintes rexistros de recursos (a maiores dos rexistros NS e SOA imprescindibles):
Tipo A: lukeskywalker con IP 192.168.20.101
Tipo A: benskywalker con IP 192.168.20.102
Tipo A: obiwankenobi con IP 192.168.56.152 e 192.168.56.153
Tipo A: hansolo con IP 192.168.56.105
Tipo A: leia con IP 192.168.56.106
Tipo A: anakinsolo con IP 192.168.56.106
Tipo CNAME mestrejedi a obiwankenobi
TIPO MX con prioridade 10 sobre o equipo hansolo
TIPO TXT "thon" con "un Jedi debe sentir a tensión entre os dous lados da Forza"
TIPO NS con benskywalker
Pega no documento de entrega a captura dos rexistros creados


![imaxe7](/tarefa1_2/imaxes/imaxe7.png)

4. Instala unha zona de resolución inversa que teña que ver co enderezo do equipo lukeskywalker, e engade rexistros PTR para os rexistros tipo A do exercicio anterior. Pega no documento de entrega o a captura dos rexistros da zona.

![imaxe8](/tarefa1_2/imaxes/imaxe8.png)

![imaxe9](/tarefa1_2/imaxes/imaxe9.png)

5. Comproba que podes resolver os distintos rexistros de recursos. Pega no documento de entrega a saída dos comandos:
nslookup lukeskywalker.academia.jedi localhost
nslookup hansolo.academia.jedi localhost
nslookup leia.academia.jedi localhost
nslookup anakinsolo.academia.jedi localhost
nslookup academia.jedi localhost
nslookup -q=mx academia.jedi localhost
nslookup -q=ns academia.jedi localhost
nslookup -q=soa academia.jedi localhost
nslookup -q=txt thon.academia.jedi localhost
nslookup 192.168.56.101 localhost

![imaxe10](/tarefa1_2/imaxes/imaxe10.png)


![imaxe11](/tarefa1_2/imaxes/imaxe11.png)


![imaxe12](/tarefa1_2/imaxes/imaxe12.png)