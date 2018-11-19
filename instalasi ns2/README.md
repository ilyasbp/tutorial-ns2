# Instalasi NS2
## 1. Download file arsip Installer NS2
Download file ns2 di [sini](http://sourceforge.net/projects/nsnam/files/latest/download)
## 2. Ekstrak arsip ns2
File bisa diekstrak di folder sembarang. tetapi di sini agar rapi buat folder `Program` dulu di direktori `Home`:
	
	cd ~
	mkdir Program
Ekstrak filenya
	
	cd ~/Program
	tar -xvzf ns-allinone-2.35.tar.gz

## 3. Install dependencies & GCC
Install dependencies:
	
	sudo apt-get install build-essential autoconf automake libxmu-dev
Install GCC:
	
	sudo apt-get install GCC

## 4. Ubah sesuatu di dalam folder ns
buka file ls.h di dalam folder ns tepatnya di linkstate

	gedit ~/Program/ns-allinone-2.35/ns-2.35/linkstate/ls.h
pada baris ke 137, ubah `error` menjadi `this->error`

## 5. Mulai instalasi
Pindah ke folder ns

	cd ~/Downloads/ns-allinone-2.35/
lalu install

	sudo ./install

## 6. Setting environment
masukkan perintah:

	sudo gedit ~/.bashrc
lalu masukkan baris berikut ini (rekomendasi: di akhir baris):

	# LD_LIBRARY_PATH
	OTCL_LIB=/home/rusaku/ns-allinone-2.35/otcl-1.14
	NS2_LIB=/home/rusaku/ns-allinone-2.35/lib
	X11_LIB=/usr/X11R6/lib
	USR_LOCAL_LIB=/usr/local/lib
	export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$OTCL_LIB:$NS2_LIB:$X11_LIB:$USR_LOCAL_LIB
	# TCL_LIBRARY
	TCL_LIB=/home/rusaku/ns-allinone-2.35/tcl8.5.10/library
	USR_LIB=/usr/lib
	export TCL_LIBRARY=$TCL_LIB:$USR_LIB
	# PATH
	XGRAPH=/home/rusaku/ns-allinone-2.35/bin:/home/rusaku/ns-allinone-2.35/tcl8.5.10/unix:/home/rusaku/ns-allinone-2.35/tk8.5.10/unix
	#the above two lines beginning from xgraph and ending with unix should come on the same line
	NS=/home/rusaku/ns-allinone-2.35/ns-2.35/ 
	NAM=/home/rusaku/ns-allinone-2.35/nam-1.15/ 
	PATH=$PATH:$XGRAPH:$NS:$NAM

lalu ganti nama user `rusaku` menjadi nama usermu

contoh: `OTCL_LIB=/home/**rusaku**/ns-allinone-2.35/otcl-1.14` menjadi `OTCL_LIB=/home/**bejo**/ns-allinone-2.35/otcl-1.14`
Restart linux

Lalu coba masukkan perintah ns di terminal

Selesai :)