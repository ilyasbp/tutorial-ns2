# Instalasi NS2 di Linux Mint / Ubuntu
## 1. Download dan Ekstrakfile arsip Installer NS2
Download file ns2 di [sini](http://sourceforge.net/projects/nsnam/files/latest/download)

File bisa diekstrak di folder sembarang. Tetapi di sini agar rapi buat folder `Program` dulu di direktori `Home`:
	
	cd ~
	mkdir Program
Ekstrak filenya
	
	cd ~/Program
	tar -xvzf ns-allinone-2.35.tar.gz

## 3. Install dependencies, gcc, dan software pendukung
Install dependencies:
	
	sudo apt-get install build-essential autoconf automake libxmu-dev
Install GCC:
	
	sudo apt-get install GCC

Install gedit:

	sudo apt-get install gedit


## 4. Ubah sesuatu di dalam folder ns
buka file ls.h di dalam folder ns tepatnya di linkstate

	gedit ~/Program/ns-allinone-2.35/ns-2.35/linkstate/ls.h
lalu pada baris ke 137, ubah `erase` menjadi `this->erase` seperti pada gambar

![](img/ls.h.png)

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
	OTCL_LIB=/home/Program/rusaku/ns-allinone-2.35/otcl-1.14
	NS2_LIB=/home/Program/rusaku/ns-allinone-2.35/lib
	X11_LIB=/usr/X11R6/lib
	USR_LOCAL_LIB=/usr/local/lib
	export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$OTCL_LIB:$NS2_LIB:$X11_LIB:$USR_LOCAL_LIB
	# TCL_LIBRARY
	TCL_LIB=/home/Program/rusaku/ns-allinone-2.35/tcl8.5.10/library
	USR_LIB=/usr/lib
	export TCL_LIBRARY=$TCL_LIB:$USR_LIB
	# PATH
	XGRAPH=/home/Program/rusaku/ns-allinone-2.35/bin:/home/Program/rusaku/ns-allinone-2.35/tcl8.5.10/unix:/home/Program/rusaku/ns-allinone-2.35/tk8.5.10/unix
	#the above two lines beginning from xgraph and ending with unix should come on the same line
	NS=/home/Program/rusaku/ns-allinone-2.35/ns-2.35/ 
	NAM=/home/Program/rusaku/ns-allinone-2.35/nam-1.15/ 
	PATH=$PATH:$XGRAPH:$NS:$NAM

lalu ganti nama user `rusaku` menjadi nama usermu. Contoh, misal nama usermu `bejo`.

ubah `OTCL_LIB=/home/Program/rusaku/ns-allinone-2.35/otcl-1.14` menjadi `OTCL_LIB=/home/Program/bejo/ns-allinone-2.35/otcl-1.14`

dan seterusnya

cara cepatnya:

	1. ctrl + H
	2. find: rusaku
	3. replace with: bejo
	4. replace all

## 7. Tes apakah ns2 sudah terinstall dengan benar

**Restart linux dulu**

Lalu coba masukkan perintah ns di terminal.

Pastikan muncul seperti pada gambar

![](img/ns-test.png)

Selesai :)