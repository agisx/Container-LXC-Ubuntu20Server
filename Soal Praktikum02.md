<h4>Nama : Dewa Nusantara MP
           Agi Lobita J.M</h4>
<h4>NIM  : 1202190053
           1202190031</h4>

<h1>Ansbile</h1>
<ol>
  <li>Create a new lxc with the folcan version with the same setup, namely lxc php7 and lxc landing</li>
  sudo lxc-create -n [name] -t download -- --dist ubuntu --release focal --arch amd64 --force-cache --no-validate --server images.linuxcontainers.org 
  <!-- Setup lxc -->
  <ol type="A">
    <h5>Initial Landing and PHP7 Configuration<h5>
    <li>Install net tools, apt install nano net-tools curl</li> 
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/0.%20Install%20net.PNG?raw=true"> 
    <li>Change Ip, both are php7 then sudo nano /etc/netplan/10-lxc.yaml</li>
    <ol type="i"> 
      <li>Ip landing : 10.0.3.103, Ip php7 : 10.0.3.101</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/0.%20Setting%20ip.PNG"> 
      <li>sudo netplan apply; ifconfig</li>
    </ol>
    <li>Installing ssh and python, apt install openssh-server python</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/0.%20Install%20python%20and%20ssh.PNG?raw=true" alt=""> 
    <li>Enable root user, nano /etc/ssh/sshd_config</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/0.%20Grant%20root%20access.PNG?raw=true" alt=""> 
    <li>Restart ssh service, sudo service sshd restart</li>
    <li>Change the password, passwd</li>
    <q>Do it on both lxc</q>
    <li>If you have finished both setup, do: ssh root@lxc_php7.dev and ssh root@lxc_landing.dev, enter the password</li>  
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/0.1%20Ubu%207%20SSH.PNG?raw=true" alt=""> 
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/0.1%20Ubu%20landing%20SSH.PNG?raw=true" alt=""> 
  </ol>
  <li>Creating ansible folder, prak2-ansible example</li> 
  <li>Create ansible hosts file group</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/0.1%20hosts%20all.PNG?raw=true" alt="">
  <li>Check the connection, ansible -i hosts -m ping all -k</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/0.%20Test%20koneksi%20ssh.PNG?raw=true" alt="">
  <li>Create roles folder</li>  
  <ol>
    <h2>Laravel 8 as landing page</h2>
    <li>Creating ansible file, example deploy-landing-app.yml</li>
    <li>Create to load roles in a folder, for example landing</li>
    <ol type="a">
      <h4>Ansible</h4>
      <li>Host deploy</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/hosts%20landing.PNG?raw=true">
      <li>Install server and laravel requirements</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/1.1%20Install%20kebutuhan%20laravel%20dan%20server.PNG?raw=true">
      <li>Looking for a repository with php7.4</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/3.1%20Find%20php%20repos.PNG?raw=true">
      <li>Install nginx and php7</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/3.2%20Install%20php7.4%20nginx.PNG?raw=true">
      <li>Clone laravel</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/1.2%20Find%20laravel%20repo.PNG?raw=true">
      <li>Config nginx</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/3.3%20Setup%20for%20nginx%20(templates).PNG?raw=true">
      <li>Config laravel</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/1.3%20Setup%20for%20laravel.PNG?raw=true">
      <li>Add hosts to hosts file</li>
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
    <h2>Wordpress as blog</h2>
    <li>Creating ansible files, example deploy-blog-app.yml</li>
    <ol type="a">
      <h4>Ansible</h4>
      <li>Host deploy</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/hosts%20blog.PNG?raw=true">
      <li>Install server and wordpress needs</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/2.1%20Install%20kebutuhan%20laravel%20dan%20server.PNG?raw=true">
      <li>Search repository with php7.4</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/3.1%20Find%20php%20repos.PNG?raw=true">
      <li>Install nginx and php7</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/3.2%20Install%20php7.4%20nginx.PNG?raw=true">
      <li>Clone wordpress</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/2.3%20Find%20wp%20repo.PNG?raw=true">
      <li>Config nginx</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/3.3%20Setup%20for%20nginx%20(templates).PNG?raw=true">
      <li>Config wordpress</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/2.1%20Setup%20for%20wordpress.PNG?raw=true">
      <li>Add host to hosts file</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/3.4%20Add%20host%20to%20hosts%20file.PNG?raw=true"> 
      <li>Nginx template</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/2.2%20Nginx%20template.PNG?raw=true">
      <li>wp-config template</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/2.%20Wp%20template.PNG">
      <li>Restart php</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/5.%20Restart%20PHP.PNG?raw=true"> 
      <li>Config db for blog</li>
      <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/2.5%20db%20config%20for%20blog.PNG?raw=true"> 
    </ol>
    <li>Run oh yeah</li> 
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/2.3%20run%20blog.PNG?raw=true">
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/2.4%20view.PNG?raw=true">
  </ol>
  <li>VM nginx config</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/vm.config.png?raw=true">
  <li>Check all</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum02/Chek%20all.PNG?raw=true">
</ol>
