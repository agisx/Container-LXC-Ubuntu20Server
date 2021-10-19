[**1. Membuat Container**]

1. Install lxc (sudo apt-get install lxc lxctl lxc-templates net-tools -y)
2. Mengubah ip dan setting ke static
	a. Ubah /etc/netplan/00-installer-config.yaml
	b. Kemudian restart network-nya
	c. Check ip-nya dengan ifconfig
3.  Buat 2 kontainer untuk app berbasis php
	
	a. PHP 5
		i. Ubah IP dan dijadikan static
		ii. Buat file config di (/etc/nginx/sites-available)
		iii. Kemudian buat symlink di (/etc/nginx/sites-enable)
		iv. Buat juga folder dan html file
		v. Masukkan ip server di hosts file
		vi. Restart dan cek respon server
	b. PHP 7
		i. Ubah IP dan dijadikan static
		ii. Buat file config di (/etc/nginx/sites-available)
		iii. Kemudian buat symlink di (/etc/nginx/sites-enable)
		iv. Buat juga folder dan html file
		v. Masukkan ip server di hosts file
		vi. Restart dan cek respon server
4. Setup vm host ke kontainer
	a. Keluar dari kontainer dan cek ip kontainer
	b. Masukkan semua ip container di hosts file vm
	c. Cek ip dengan ping
5. Setup vm host ke windows
	a. Membuat file config server di vm host 
	b. Menambahkan ip kontainer ke hosts file vm
	c. Check respon semua kontainer
	d. Menambahkan vm host ip ke hosts file windows
	e. Check di web browser windows
6. [opsional] VM sebagai home page
	a. Membuat file dan folder html di vm host
	b. Restart nginx dan cek respon
	c. Cek kontainer dan vm host di web browser windows
