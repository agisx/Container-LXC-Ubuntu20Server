<h1>Tugas Besar Sistem Administrasi</h1>
<h2>List Contents</h2>
<ol>
  <li><a href="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/Tugas%20Besar.md#teknologi-yang-digunakan">Teknologi yang Digunakan</a></li>
  <li><a href="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/Tugas%20Besar.md#arsitektur-jaringan">Arsitektur Jaringan</a></li>
  <li><a href="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/Tugas%20Besar.md#arsitektur-load-balancing">Arsitektur Load Balancing</a></li>
  <li><a href="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/Tugas%20Besar.md#ansible">Ansible</a></li>
  <ol>
    <li><a href="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/Tugas%20Besar.md#all">All</a></li>
    <li><a href="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/Tugas%20Besar.md#laravel-8">Laravel</a></li>
    <li><a href="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/Tugas%20Besar.md#codeigniter-3">Codeigniter</a></li>
    <li><a href="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/Tugas%20Besar.md#wordpress-lastest">Wordpress</a></li>
    <li><a href="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/Tugas%20Besar.md#yii2">Yii2</a></li>
    <li><a href="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/Tugas%20Besar.md#dns">DNS</a></li>
    <li><a href="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/Tugas%20Besar.md#other-ansible-for-handler">Other ansible</a></li> 
  </ol>
  
  <li><a href=""></a></li>
  <li><a href=""></a></li>
  <li><a href=""></a></li>
  <li><a href=""></a></li>
</ol>

<h2>Teknologi yang Digunakan</h2>
<ol> 
  <li>VM Ubuntu 20.04 (menggunakan metode bridge network, dan static ip)</li>
  <li>Nginx</li>
  <li>6 instance LXC ubuntu 20.04 PHP 7.4</li>
  <li2 instance LXC debian 10 PHP 5.6></li>
  <li>1 instance LXC debian 10 mariadb server</li>
  <li>Semua instalasi menggunakan Ansible</li>
  <li>kelompok13.fpsas/ menggunakan laravel 8</li>
  <li>news.kelompok13.fpsas menggunakan wordpress terbaru</li>
  <li>kelompok13.fpsas/product menggunakan YII 2.0</li>
  <li>kelompok13.fpsas/app menggunakan Code Igniter 3</li>
</ol>

<h2>Arsitektur Jaringan</h2>
<img src="https://raw.githubusercontent.com/aldonesia/Sistem-Administrasi-Server-2021/master/Final%20Project/assets/arsitektur.png" alt="Arsitektur Jaringan">

<h2>Arsitektur Load Balancing</h2>
<img src="" alt="">

<h2>Teknologi yang Digunakan</h2>
<ol>
  <li></li>
</ol>
<img src="" alt="">

<h2>Ansible</h2>
<img src="" alt="">
<ol>
  <h3>All</h3>
  <li>Run Ansibles</li>
  <img src="" alt="">
  <img src="" alt="">
</ol>
<h3>Laravel 8</h3>
<a href="https://github.com/agisx/Container-LXC-Ubuntu20Server/tree/main/images/tubes/laravel">Laravel's Ansible</a>
<ol>
  <li>Deploy all laravels' hosts</li>
  <img src="https://raw.githubusercontent.com/agisx/Container-LXC-Ubuntu20Server/main/images/tubes/laravel/all%20hosts.PNG">
  <li>Laravel's Tasks</li>
  <ol type="a">
    <li>Install requirement items, add Repository, and clone the laravel's git</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/laravel/1.1.PNG?raw=true">
    <ul> 
      <li>Delete the files' apt chache</li>
      <li>Install php7 package requirements</li>
      <li>Ignore yes to skip thee rror from lxc's installed yet package</li>
      <li>Add php repository and add key for php packages</li>
    </ul>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/laravel/1.2.PNG?raw=true">
    <ul> 
      <li>Add php repository</li>
      <li>Install nginx requirements</li>
      <li>Clone the laravel's git</li>
    </ul>
    <li>Setup the server file</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/laravel/1.3.PNG?raw=true">
    <ul> 
      <li>Copy nginx files template</li>
      <li>Create the symlink</li>
      <li>Copy laravel's file config</li>
      <li>Generate the key</li>
      <li>Change the permission</li>
    </ul>
    <li>Write up the host in hosts file</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/laravel/1.4.PNG?raw=true">
    <li>Nginx's config file</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/laravel/5.PNG?raw=true">
  </ol>
  <li></li>
  <li></li>
  <li></li>
  <li></li>
  <li></li>
  <li></li>
</ol>
<ol>
  <h3>Codeigniter 3</h3>
  <li>Run Codeigniter's Ansible</li>
  <ol>
    <li><a href="">Codeigniter's Ansible</a></li>
    <img src="">
  </ol>
  <li></li>
  <li></li>
  <li></li>
  <li></li>
  <li></li>
  <li></li>
</ol>
<ol>
  <h3>Wordpress Lastest</h3>
  <li>Run Wordpress's Ansible</li>
  <ol>
    <li><a href="">Wordpress's Ansible</a></li>
    <img src="" alt="">
  </ol>
  <li></li>
  <li></li>
  <li></li>
  <li></li>
  <li></li>
  <li></li>
</ol>
<ol>
  <h3>Yii2</h3>
  <li>Run Yii2's Ansible</li>
  <ol>
    <li><a href="">Yii2's Ansible</a></li>
    <img src="" alt="">
  </ol>
  <li></li>
  <li></li>
  <li></li>
  <li></li>
  <li></li>
  <li></li>
</ol>
<ol>
  <h3>DNS</h3>
  <li>Run DNS's Ansible</li>
  <ol>
    <li><a href="">DNS's Ansible</a></li>
    <img src="" alt="">
  </ol>
  <li></li>
  <li></li>
  <li></li>
  <li></li>
  <li></li>
  <li></li>
  <li></li>
  <li></li>
</ol>
<ol>
  <h3>Other ansible for handler</h3>
  <li></li> 
</ol>




