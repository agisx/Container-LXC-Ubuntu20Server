<h3>Tools<h3>
1. Ansible
Ansible is an open source IT automation engine that automates provisioning, configuration management, application deployment, orchestration, and many other IT processes. -
<a href="https://www.redhat.com/en/topics/automation/learning-ansible-tutorial">Red Hat</a>
<br>
<br>
2. Python
In this assignment, Python itself can be used for execute the script of YAML, also it can be used for reading the script with the group technique or phyton syntax in general.
<br>
<br>
3. Lynx 
Lynx is a terminal-based web browser for all Linux distributions. -
<a href="https://www.geeksforgeeks.org/using-lynx-to-browse-the-web-from-the-linux-terminal/">Geeksforgeeks</a>
<h1>Ansbile</h1>
<ol>
  <li>Membuat lxc baru dengan versi folcan dengan setup yang sama, yaitu lxc php7 dan lxc landing</li>
  sudo lxc-create -n [name] -t download -- --dist ubuntu --release focal --arch amd64 --force-cache --no-validate --server images.linuxcontainers.org 
  <!-- Setup lxc -->
  <ol type="A">
    <h5>Konfigurasi Awal Landing dan PHP7<h5>
    <li>Memasang net tools, apt install nano net-tools curl</li> 
    <li>Rubah Ip, keduanya adalah php7 maka, sudo nano /etc/netplan/10-lxc.yaml</li>
    <ol type="i"> 
      <li>Ip landing : 10.0.3.103, Ip php7 : 10.0.3.101</li>
      img
      <li>sudo netplan apply; ifconfig</li>
    </ol>
    <li>Memasang ssh dan python, apt install openssh-server python</li>
    <li>Enable root user, nano /etc/ssh/sshd_config</li>
    <li>Restart ssh service, sudo service sshd restart</li>
    <li>Ganti password, passwd</li>
    <q>Lakukan dikedua lxc</q>
    <li>Jika sudah selesai setup dikeduanya, lakukan : ssh root@lxc_php7.dev dan ssh root@lxc_landing.dev, masukkan password</li> 
  </ol>
  <li>Membuat folder ansible, contoh prak2-ansible</li> 
  <li>Membuat group ansible host file</li>
  img
  <li>Tes koneksi, ansible -i hosts -m ping all -k</li>
  <li>Membuat folder roles</li> 
  img
  <ol>
    <h2>Laravel 8 sebagai landing page</h2>
    <li>Membuat file ansible, contoh deploy-landing-app.yml</li>
    img
    <li>Mencari repository php 7, ppa:ondrej/php</li>
    
  </ol>
  <ol>
    <h2>Wordpress sebagai blog</h2>
    <li></li>
    
  </ol>
  <li></li>
  <li></li>
  <li></li>
  <li></li>
  <li></li>
  <li></li>
  <li></li>
  <li></li>
  <li></li>
  <li></li>
</ol>
