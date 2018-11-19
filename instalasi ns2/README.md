# Instalasi NS2
## 1. Download file arsip Installer NS2
Download file ns2 di [sini](http://sourceforge.net/projects/nsnam/files/latest/download)
## 2. Ekstrak arsip ns2
1. file bisa diekstrak di folder sembarang. tetapi di sini agar rapi buat folder `Program` dulu di direktori `Home`:
	
	`cd ~
	mkdir Program`
2. Ekstrak filenya
	
	`cd ~/Program
	tar -xvzf ns-allinone-2.35.tar.gz`
1. Install dependencies:
	sudo apt-get install build-essential autoconf automake libxmu-dev
1. Install GCC:
	sudo apt-get install gcc
1. Ubah sesuatu di dalam folder ns
	gedit ~/Downloads/ns-allinone-2.35/ns-2.35/linkstate
1. Mulai instalasi
	cd ~/Downloads/ns-allinone-2.35/
	sudo ./install
1. Setting environment
	masukkan perintah:
		sudo gedit ~/.bashrc
	lalu masukkan baris berikut ini (rekomendasi: di paling bawah):
		# LD_LIBRARY_PATH
		OTCL_LIB=/home/akshay/ns-allinone-2.35/otcl-1.14
		NS2_LIB=/home/akshay/ns-allinone-2.35/lib
		X11_LIB=/usr/X11R6/lib
		USR_LOCAL_LIB=/usr/local/lib
		export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$OTCL_LIB:$NS2_LIB:$X11_LIB:$USR_LOCAL_LIB
		# TCL_LIBRARY
		TCL_LIB=/home/akshay/ns-allinone-2.35/tcl8.5.10/library
		USR_LIB=/usr/lib
		export TCL_LIBRARY=$TCL_LIB:$USR_LIB
		# PATH
		XGRAPH=/home/akshay/ns-allinone-2.35/bin:/home/akshay/ns-allinone-2.35/tcl8.5.10/unix:/home/akshay/ns-allinone-2.35/tk8.5.10/unix
		#the above two lines beginning from xgraph and ending with unix should come on the same line
		NS=/home/akshay/ns-allinone-2.35/ns-2.35/ 
		NAM=/home/akshay/ns-allinone-2.35/nam-1.15/ 
		PATH=$PATH:$XGRAPH:$NS:$NAM
1. Restart linux
1. Coba masukkan perintah ns di terminal
1. Selesai :)