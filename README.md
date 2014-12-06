Ceos-Emulator

Agradecemos de coração os projetos que fizeram do Ceos-Emulator possível.

eAthena, rAthena e Hercules, cujos códigos são utilizados no Ceos-Emulator.

=======
índice
---------
* 1 - O que é o Ceos-Emulator?
* 2 - Requesitos
* 3 - Instalação
* 4 - Problemas
* 5 - Links Úteis
* 6 - Outros

1. O que é o Ceos-Emulator
---------

Ceos é um projeto de software colobarativo para a emulação de envio de pacotes do MMORPG Ragnarok Online.
Escrito em C, o programa é vestáril e provém NPCs, portais e modificações. O projeto é gerenciado
por um grupo de voluntários localizados ao redor do Brasil e dá suporte aos seus utilizadores.
Ceos-Emulator é uma continuação do rAthena, cujo também veio de seu antecessor, o eAthena.

2. Requesitos
---------

Antes de Instalar o Ceos-Emulator, há certas ferramentas e aplicações que você irá precisar.

* Windows
	* MySQL ( http://www.mysql.com/downloads/mysql/ )
	* MySQL Workbench ( http://www.mysql.com/downloads/workbench/ )
	* MS Visual C++ ( http://www.microsoft.com/visualstudio/en-us/products/2010-editions/visual-cpp-express )
	* Git for Windows ( http://code.google.com/p/tortoisegit/ )
	* MSysGit ( http://msysgit.github.io/ or https://github.com/msysgit/git/releases )

* Linux
	* gcc
	* make
	* mysql
	* mysql-devel
	* mysql-server
	* pcre-devel
	* zlib-devel
	* git

3. Instalação 
---------

* Windows
	* Crie uma pasta para baixar o Ceos-Emulator
	* Clique em Download Zip na página do Git

* Linux
	* Type:
		* (For CentOS)

				yum install gcc make mysql mysql-devel mysql-server pcre-devel zlib-devel
				rpm -Uvhhttp://repo.webtatic.com/yum/centos/5/latest.rpm
				yum install --enablerepo=webtatic git-all
				yum install --enablerepo=webtatic --disableexcludes=main git-all
		* (For Debian)

				apt-get install git make gcc libmysqlclient-dev zlib1g-dev libpcre3-dev
	* Type:

				mysql_secure_installation
	* Start your MySQL server
	* Setup a MySQL user:

				CREATE USER 'rathena'@'localhost' IDENTIFIED BY 'password';
	* Assign permissions:

				GRANT SELECT,INSERT,UPDATE,DELETE ON `rathena\_rag`.* TO 'rathena'@'localhost';
	* Clone a GIT repository:

				git clone https://github.com/rathena/rathena.git ~/rathena
	* Insert SQL files:

				mysql --user=root -p rathena_rag < trunk/sql-files/main.sql (and others)
	* Configure and compile:

				./configure && make clean && make sql
	* When you're ready, start the servers:

				./athena-start start



4. Problemas
---------

Se você está dendo problemas para iniciar seu servidor, o primeiro a fazer é checar o que acontece no console.

Exemplo:

* Você recebe um erro em seu map-server com algo parecido:

			[Error]: npc_parsesrcfile: Unable to parse, probably a missing or extra TAB in 
				file 'npc/custom/jobmaster.txt', line '17'. Skipping line...
				* w1=prontera,153,193,6 script
				* w2=Job Master
				* w3=123,{
				* w4=

   Se você olhar bem o erro, ele está lhe dizendo o que fazer.

				* w1=prontera,153,193,6 script
				
   O emulador está pedindo para utilizar os TAB no cabeçalho, em nosso fórum você entenderá melhor isto.




5. Linkst Úteis
---------
* Ceos-Emulator Fórum
	* link?

* GIT Repository
	* https://github.com/rathena/rathena

* Wiki rAthena
	* http://rathena.org/wiki/


6. Outros
---------

Ceos-Emulator possui uma vasta coleção de documentos de ajuda e exemplo de script, muitos criados pelos usuários do rAthena e traduzidor pelo Ceos-Emulator. A pasta se chama "Guia do Emulador".
