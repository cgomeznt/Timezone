### Metodo 1: /etc/localtime 
```
	# ls -l /etc/localtime*
	-rw-r--r-- 1 root root 240 sep 19  2015 /etc/localtime
```
```
	# cat /etc/localtime 
	TZif2�,<���HG[�p���D������������CMTVETTZif2
		                                                  ����i�@�����,<�������HG[�p���@���D���������LMTCMTVET
	VET4:30
```
```
	# mv /etc/localtime /etc/localtime.old
```
```
	# cd /tmp
```
```
	# wget http://ftp.debian.org/debian/pool/main/t/tzdata/tzdata_2016d-2_all.deb
```
```
	# dpkg-deb -x tzdata_2016d-2_all.deb .
```
```
	# ls -ld usr/
```
```
	# cat usr/share/zoneinfo/America/Caracas 
	TZif2�,<���HG[�p���D������������CMTVETTZif2
		                                                  ����i�@�����,<�������HG[�p���@���D���������LMTCMTVET
	VET4
```
```
	# mv Caracas /usr/share/zoneinfo/America/Caracas
```
```
	# rm /etc/localtime
```
```
	# ln -s /usr/share/zoneinfo/America/Caracas /etc/localtime
```
```
	# date -u
	mié may 11 00:29:02 UTC 2016
	# date
	mar may 10 20:29:04 VET 2016
```

### Metodo 2: /etc/timezone
```
# cat /etc/timezone
America/Caracas
```
```
# vi /etc/timezone
America/La_Paz
```
```
# export TZ=America/La_Paz
```

### Metodo 3: En GNU/Linux que no sean Debian.
```
	# ls -l /etc/localtime*
	-rw-r–r– 1 root root 240 sep 19 2015 /etc/localtime
	# cat /etc/localtime
	VET4:30
	# mv /etc/localtime /etc/localtime.old
	# cd /tmp
	# wget http://ftp.debian.org/debian/pool/main/t/tzdata/tzdata_2016d-2_all.deb
	# ar -x tzdata_2016d-2_all.deb
	# tar -xvJf data.tar.xz
	# ls -ld usr/
	# cat usr/share/zoneinfo/America/Caracas
	VET4
	# mv usr/share/zoneinfo/America/Caracas /usr/share/zoneinfo/America/Caracas
	# ln -s /usr/share/zoneinfo/America/Caracas /etc/localtime
	# date -u
	mié may 11 00:29:02 UTC 2016
	# date
	mar may 10 20:29:04 VET 2016
```


