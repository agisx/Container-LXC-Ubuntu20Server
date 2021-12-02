<h4>Nama : DEWA NUSANTARA MURDOKO PUTRA</h4>
<h4>NIM  : 1202190053</h4>

<h4>Nama : Agi Lobita J.M</h4>
<h4>NIM  : 1202190031</h4>

<h1>Ansbile</h1>
<ol>
  <li>Membuat lxc baru dengan versi folcan dengan setup yang sama, yaitu lxc php7 dan lxc landing</li>
  sudo lxc-create -n [name] -t download -- --dist ubuntu --release focal --arch amd64 --force-cache --no-validate --server images.linuxcontainers.org 
  <!-- Setup lxc -->
  <ol type="A">
    <h5>Konfigurasi Awal Landing dan PHP7<h5>
    <li>Memasang net tools, apt install nano net-tools curl</li> 
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/0.%20Install%20net.PNG?raw=true"> 
    <li>Rubah Ip, keduanya adalah php7 maka sudo nano /etc/netplan/10-lxc.yaml</li>
    <ol type="i"> 
      <li>Ip landing : 10.0.3.103, Ip php7 : 10.0.3.101</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/0.%20Setting%20ip.PNG"> 
      <li>sudo netplan apply; ifconfig</li>
    </ol>
    <li>Memasang ssh dan python, apt install openssh-server python</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/0.%20Install%20python%20and%20ssh.PNG?raw=true" alt=""> 
    <li>Enable root user, nano /etc/ssh/sshd_config</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/0.%20Grant%20root%20access.PNG?raw=true" alt=""> 
    <li>Restart ssh service, sudo service sshd restart</li>
    <li>Ganti password, passwd</li>
    <q>Lakukan dikedua lxc</q>
    <li>Jika sudah selesai setup dikeduanya, lakukan : ssh root@lxc_php7.dev dan ssh root@lxc_landing.dev, masukkan password</li>  
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/0.1%20Ubu%207%20SSH.PNG?raw=true" alt=""> 
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/0.1%20Ubu%20landing%20SSH.PNG?raw=true" alt=""> 
  </ol>
  <li>Membuat folder ansible, contoh prak2-ansible</li> 
  <li>Membuat group ansible host file</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/0.1%20hosts%20all.PNG?raw=true" alt="">
  <li>Tes koneksi, ansible -i hosts -m ping all -k</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/0.%20Test%20koneksi%20ssh.PNG?raw=true" alt="">
  <li>Membuat folder roles</li>  
  <ol>
    <h2>Laravel 8 sebagai landing page</h2>
    <li>Membuat file ansible, contoh deploy-landing-app.yml</li>
    <li>Buat untuk load roles di sebuah folder, contoh landing</li>
    <ol type="a">
      <h4>Ansible</h4>
      <li>Host deploy</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/hosts%20landing.PNG?raw=true">
      <li>Install kebutuhan server dan laravel</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/1.1%20Install%20kebutuhan%20laravel%20dan%20server.PNG?raw=true">
      <li>Mencari repository dengan php7.4</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/3.1%20Find%20php%20repos.PNG?raw=true">
      <li>Install nginx dan php7</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/3.2%20Install%20php7.4%20nginx.PNG?raw=true">
      <li>Clone laravel</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/1.2%20Find%20laravel%20repo.PNG?raw=true">
      <li>Config nginx</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/3.3%20Setup%20for%20nginx%20(templates).PNG?raw=true">
      <li>Config laravel</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/1.3%20Setup%20for%20laravel.PNG?raw=true">
      <li>Tambahkan host ke hosts file</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/3.4%20Add%20host%20to%20hosts%20file.PNG?raw=true">
      <li>Nginx template</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/1.4%20Nginx%20template.PNG?raw=true">
      <li>.env template</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/1.5%20.env%20template.PNG?raw=true">
      <li>Restart php</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/5.%20Restart%20PHP.PNG?raw=true"> 
    </ol>  
    <li>Run oh yeah</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/1.6%20run%20landing.PNG?raw=true"> 
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/1.7%20view.PNG?raw=true"> 
  </ol>
  <ol>
    <h2>Wordpress sebagai blog</h2>
    <li>Membuat file ansible, contoh deploy-blog-app.yml</li>
    <ol type="a">
      <h4>Ansible</h4>
      <li>Host deploy</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/hosts%20blog.PNG?raw=true">
      <li>Install kebutuhan server dan wordpress</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/2.1%20Install%20kebutuhan%20laravel%20dan%20server.PNG?raw=true">
      <li>Mencari repository dengan php7.4</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/3.1%20Find%20php%20repos.PNG?raw=true">
      <li>Install nginx dan php7</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/3.2%20Install%20php7.4%20nginx.PNG?raw=true">
      <li>Clone wordpress</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/2.3%20Find%20wp%20repo.PNG?raw=true">
      <li>Config nginx</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/3.3%20Setup%20for%20nginx%20(templates).PNG?raw=true">
      <li>Config wordpress</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/2.1%20Setup%20for%20wordpress.PNG?raw=true">
      <li>Tambahkan host ke hosts file</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/3.4%20Add%20host%20to%20hosts%20file.PNG?raw=true"> 
      <li>Nginx template</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/2.2%20Nginx%20template.PNG?raw=true">
      <li>wp-config template</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/2.%20Wp%20template.PNG">
      <li>Restart php</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/5.%20Restart%20PHP.PNG?raw=true"> 
      <li>Config db untuk blog</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/2.5%20db%20config%20for%20blog.PNG?raw=true"> 
    </ol>
    <li>Run oh yeah</li> 
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/2.3%20run%20blog.PNG?raw=true">
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/2.4%20view.PNG?raw=true">
  </ol>
  <li>VM nginx config</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/vm.config.png?raw=true">
  <li>Cek semua</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/Chek%20all.PNG?raw=true">
</ol>
