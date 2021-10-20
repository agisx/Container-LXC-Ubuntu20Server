[**Container dengan LXC di Ubuntu20 Server**]

1. Install lxc (sudo apt-get install lxc lxctl lxc-templates net-tools -y)
![alt text](https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Praktikum01/1.%20Prepare%20the%20server.PNG?raw=true)

2. Mengubah ip dan setting ke static
	
	<ol type="a">
		<li>Ubah /etc/netplan/00-installer-config.yaml</li>
		<li>Kemudian restart network-nya</li>
		<li>Check ip-nya dengan ifconfig</li>
	
	![alt text](https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Praktikum01/1.1.%20Change%20the%20server's%20ip%20address%20to%20the%20static.PNG?raw=true)
	</ol>
3.  Buat 2 kontainer untuk app berbasis php
	
	
	![alt text](https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Praktikum01/2.%20Prepare%202%20containers.PNG?raw=true)
	
4.  Setup kontainer	
	<ol type="a"> 
		<li>PHP 5 
			<ol type="a">
				<li>Ubah IP dan dijadikan static</li>     
				<image src="https://raw.githubusercontent.com/agisx/Container-LXC-Ubuntu20Server/main/images/Praktikum01/3.1.0.%20Change%20the%20ip%20address%20and%20set%20to%20static%20mode.PNG">
				<image src="https://raw.githubusercontent.com/agisx/Container-LXC-Ubuntu20Server/main/images/Praktikum01/3.1.1.%20Check%20the%20ip.PNG">
				<li>Buat folder dan file config di (/etc/nginx/sites-available/[file name])</li>   
				<image src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Praktikum01/3.1.2.%20Create%20a%20server's%20file%20config.PNG?raw=true">
				<image src="https://raw.githubusercontent.com/agisx/Container-LXC-Ubuntu20Server/main/images/Praktikum01/3.1.3.%20The%20config.PNG">
				<br>	
				<a>source html file : (/var/www/html/lxc_php5.6/(file-file))</a>
				<li>Kemudian buat symlink di (/etc/nginx/sites-enabled)</li> 
				<image src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Praktikum01/3.1.4.%20Create%20a%20symlink.PNG?raw=true">
				<li>Buat juga folder dan html file</li> 
				<image src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Praktikum01/3.1.5.%20Create%20a%20folder%20and%20a%20html%20file.PNG?raw=true">
				<li>Masukkan ip server di hosts file</li> 
				<image src="https://raw.githubusercontent.com/agisx/Container-LXC-Ubuntu20Server/main/images/Praktikum01/3.1.6.%20Add%20server's%20ip%20to%20hosts%20file.PNG">
				<li>Restart dan cek respon server</li> 
				<image src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Praktikum01/3.1.7.%20Reload%20the%20nginx%20and%20transfer%20data%20to%20the%20server%20with%20curl.PNG?raw=true">
				<image src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Praktikum01/3.1.8.%20Respon%20OK.PNG?raw=true">
			</ol>
		</li>
		<li>PHP 7
			<ol type="i">
				<li>Ubah IP dan dijadikan static</li> 
				<image src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Praktikum01/3.2.0.%20Change%20the%20ip%20address%20and%20set%20to%20static%20mode.PNG?raw=true">
				<image src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Praktikum01/3.2.1.%20Restart%20the%20network%20service%20and%20check%20the%20ip.PNG?raw=true">
				<li>Buat file config di (/etc/nginx/sites-available)</li> 
				<image src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Praktikum01/3.2.2.%20Create%20a%20server's%20file%20config.PNG?raw=true">
				<image src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Praktikum01/3.2.3.%20The%20config.PNG?raw=true">
				<li>Kemudian buat symlink di (/etc/nginx/sites-enable)</li> 
				<image src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Praktikum01/3.2.4.%20Create%20a%20symlink.PNG?raw=true">
				<li>Buat juga folder dan html file</li> 
				<image src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Praktikum01/3.2.5.%20Create%20a%20folder%20and%20a%20html%20file.PNG?raw=true">
				<li>Masukkan ip server di hosts file</li> 
				<image src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Praktikum01/3.2.7.%20Add%20server's%20ip%20to%20hosts%20file.PNG?raw=true">
				<li>Restart nginx (nginx -s reload) dan cek respon server</li> 
				<image src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Praktikum01/3.2.8.%20Respon%20OK.PNG?raw=true">
			</ol>
		</li>
	</ol>
4. Setup vm host ke kontainer
	<ol type="a">
		<li>Keluar dari kontainer dan cek ip kontainer</li>
		<image src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Praktikum01/4.1.%20Back%20to%20the%20host%20and%20check%20the%20container.PNG?raw=true"> 
		<li>Masukkan semua ip container di hosts file vm</li>
		<image src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Praktikum01/4.2.%20Insert%20all%20container's%20ip.PNG?raw=true">
		<li>Cek koneksi dengan ping</li>
		<image src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Praktikum01/4.3.%20Check%20the%20ip.PNG?raw=true">
	</ol>
5. Setup vm host ke windows
	<ol type="a">
		<li>Membuat file config server di vm host </li>
		<image src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Praktikum01/5.1.%20Create%20a%20server's%20file%20config%20in%20vm%20host.PNG?raw=true">
		<br>
		<image src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Praktikum01/5.2.%20The%20config.PNG?raw=true">
		<li>Check respon semua kontainer</li>
		<image src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Praktikum01/5.3.1%20Respond%20OK%205.6.PNG?raw=true">
		<image src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Praktikum01/5.3.1%20Respond%20OK%207.4.PNG?raw=true">
		<li>Menambahkan vm host ip ke hosts file windows</li>
		<li>Check di web browser windows></li> 
		<image src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Praktikum01/5.4.%20Insert%20vm%20host's%20ip%20to%20windows's%20host%20%20file%20and%20check%20in%20the%20web%20browser.PNG?raw=true">
	</ol>
6. [opsional] VM sebagai home page
	<ol type="a">
		<li>Membuat file dan folder html di vm host</li>
		<image src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Praktikum01/%5Bopsional%5D%206.1.1%20Create%20a%20folder%20and%20a%20html%20file%20(vm).PNG?raw=true">
		<li>Restart nginx dan cek respon</li>
		<image src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Praktikum01/%5Bopsional%5D%206.1.2%20Respon%20OK.PNG?raw=true">
		<li>Cek kontainer dan vm host di web browser windows</li>
		<image src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Praktikum01/%5Bopsional%5D%206.1.3%20Check%20in%20web%20browser.PNG?raw=true">
	</ol> 
