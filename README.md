# Container LXC Ubuntu Server
Perancangan container dalam ubuntu server menggunakan linux container atau lxc. Container adalah metode virtualisasi tingkat sistem operasi untuk menjalankan beberapa sistem operasi yang terisolasi satu sama lain dalam satu perangkat atau satu host. Dalam hal ini adalah ubuntu server memiliki beberapa ubuntu server sebagai container didalamnya dan dapat menciptakan lingkungan development maupun production dalam satu perangkat tanpa mengganggu satu sama lain. 

<h2>List Contents</h2>
<ol>
  <li><a href="https://github.com/agisx/Container-LXC-Ubuntu20Server#teknologi-yang-digunakan">Teknologi yang Digunakan</a></li>
  <li><a href="https://github.com/agisx/Container-LXC-Ubuntu20Server#arsitektur-jaringan">Arsitektur Jaringan</a></li>
  <li><a href="https://github.com/agisx/Container-LXC-Ubuntu20Server#tabel-load-balancing">Tabel Load Balancing</a></li>
  <li><a href="https://github.com/agisx/Container-LXC-Ubuntu20Server#configuration">Vm configuration</a></li>
  <li><a href="https://github.com/agisx/Container-LXC-Ubuntu20Server#ansible">Ansible</a></li>
  <ol>
    <li><a href="https://github.com/agisx/Container-LXC-Ubuntu20Server#all-hosts">All Hosts</a></li>
    <li><a href="https://github.com/agisx/Container-LXC-Ubuntu20Server#laravel">Laravel</a></li>
    <li><a href="https://github.com/agisx/Container-LXC-Ubuntu20Server#codeigniter">Codeigniter</a></li>
    <li><a href="https://github.com/agisx/Container-LXC-Ubuntu20Server#wordpress">Wordpress</a></li>
    <li><a href="https://github.com/agisx/Container-LXC-Ubuntu20Server#yii">Yii2</a></li> 
    <li><a href="https://github.com/agisx/Container-LXC-Ubuntu20Server#database">Database</a></li>
  </ol>
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

<h2>Tabel Load Balancing</h2>
<img src="https://raw.githubusercontent.com/agisx/Container-LXC-Ubuntu20Server/686ef165047c8bc3265a10e708666bc6d4ece183/images/tubes/arsitektur%20table.PNG">

<h2>All Containers</h2>
<img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/all%20containers.PNG?raw=truee">

<h2>Configuration</h2>
<img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/load%20balancer.PNG?raw=true">
<img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/server.PNG?raw=true">
<img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/hosts.PNG?raw=true" alt="Vm Hosts">
<img src="https://raw.githubusercontent.com/agisx/Container-LXC-Ubuntu20Server/c34144ce93f38a60dab5b21ed26bad047266917d/images/tubes/window.PNG" alt="Windows Hosts">
<img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/dns%20windows.PNG?raw=true" alt="Windows DNS">

<h2>Ansible</h2>
<h3>All Hosts</h3>
<img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/all%20hosts.PNG?raw=true">
<h3>Laravel</h3>
<a href="https://github.com/agisx/Container-LXC-Ubuntu20Server/tree/main/images/tubes/laravel">Laravel's Ansible</a>
<ol>  
  <table>
    <caption>Vars</caption>
    <thead>
      <tr>
        <th>No</th>
        <th>Var Name</th>
        <th>Value</th>
        <th>Explain</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>1</td>
        <td>git_url</td>
        <td>https://github.com/laravel/laravel</td>
        <td>The laravel git</td>
      </tr> 
      <tr>
        <td>2</td>
        <td>destdir</td>
        <td>/var/www/html/laravel</td>
        <td>Destination directory for installation</td>
      </tr> 
      <tr>
        <td>3</td>
        <td>domain</td>
        <td>ansible host</td>
        <td>Get current lxc's object</td>
      </tr> 
      <tr>
        <td>4</td>
        <td>conf_name_nginx</td>
        <td>app-laravel8.conf</td>
        <td>File name</td>
      </tr> 
    </tbody>
  </table>  
  <img src="https://raw.githubusercontent.com/agisx/Container-LXC-Ubuntu20Server/main/images/tubes/laravel/0.PNG">
  <li>Deploy all laravels' hosts</li>
  <img src="https://raw.githubusercontent.com/agisx/Container-LXC-Ubuntu20Server/main/images/tubes/laravel/all%20hosts.PNG">
  <li>Laravel's Roles</li>
  <ol type="a">
    <li>Install requirement items, add Repository, and clone the laravel's git</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/laravel/1.1.PNG?raw=true">
    <ul> 
      <li>Delete the files' apt chache</li>
      <li>Install php7 package requirements</li>
      <li>Ignore yes to skip the error from lxc's installed yet package</li>
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
      <li>Install composer for laravel</li>
      <li>Generate the key</li>
      <li>Change the permission</li>
      <li>Copy database file</li>
    </ul>
    <li>Write up the host in hosts file</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/laravel/1.4.PNG?raw=true">
    <li>Nginx's config file</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/laravel/5.PNG?raw=true">
    <li>Database file</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/laravel/5.2.PNG?raw=true">
    <li>The handlers</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/handlers%20wp%20lvl%20yii.PNG?raw=true">    
  </ol>
  <li>Run laravel's ansible</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/laravel/run.PNG?raw=true">
  <li>The result</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/laravel.PNG?raw=true">
</ol>


<h3>Codeigniter</h3>
<a href="https://github.com/agisx/Container-LXC-Ubuntu20Server/tree/main/images/tubes/ci">Codeigniter's Ansible</a>
<ol>
  <table>
    <caption>Vars</caption>
    <thead>
      <tr>
        <th>No</th>
        <th>Var Name</th>
        <th>Value</th>
        <th>Explain</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>1</td>
        <td>git_url</td>
        <td>https://github.com/aldonesia/sas-ci</td>
        <td>The ci git</td>
      </tr> 
      <tr>
        <td>2</td>
        <td>destdir</td>
        <td>/var/www/html/ci</td>
        <td>Destination directory for installation</td>
      </tr> 
      <tr>
        <td>3</td>
        <td>domain</td>
        <td>ansible host</td>
        <td>Get current lxc's object</td>
      </tr> 
      <tr>
        <td>4</td>
        <td>conf_name_nginx</td>
        <td>ci3_app.conf</td>
        <td>File name</td>
      </tr> 
    </tbody>
  </table>  
  <img src="https://raw.githubusercontent.com/agisx/Container-LXC-Ubuntu20Server/main/images/tubes/ci/0.PNG">
  <li>Deploy all Codeigniters' hosts</li>
  <img src="https://raw.githubusercontent.com/agisx/Container-LXC-Ubuntu20Server/main/images/tubes/ci/all%20hosts.PNG">
  <li>Codeigniter's Roles</li>
  <ol type="a">  
    <li>Install requirement items, add Repository, and clone the Codeigniters's git</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/ci/1.1.PNG?raw=true">
    <ul> 
      <li>Delete the files' apt chache</li>
      <li>Install php7 package requirements</li>
      <li>Ignore yes to skip the error from lxc's installed yet package</li>
      <li>Add php repository and add key for php packages</li>
    </ul>    
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/ci/1.2.PNG?raw=true">
    <ul> 
      <li>Install nginx requirements</li>
      <li>Clone the ci's git</li>
      <li>Copy nginx files template</li>
      <li>Copy database template</li>
    </ul>
    <li>Setup the server file</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/ci/1.3.PNG?raw=true">
    <ul> 
      <li>Delete another nginx config</li>
      <li>Create a symlink</li>  
      <li>Write up the host in hosts file</li>
    </ul> 
    <li>Nginx's config file</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/ci/5.1.PNG?raw=true">
    <li>Database file</li>
    <img src="https://raw.githubusercontent.com/agisx/Container-LXC-Ubuntu20Server/762bb0c9be9d20a7daebc4e84ba1222fc5464757/images/tubes/ci/5.2.PNG">
    <li>The handlers</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/handlers%20ci.PNG?raw=true">
  </ol>
  
  <li>Run ci's ansible</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/ci/run.PNG?raw=true">
  <li>The result</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/ci3.PNG?raw=true">
</ol>

<h3>Wordpress</h3>
<a href="https://github.com/agisx/Container-LXC-Ubuntu20Server/tree/main/images/tubes/wp">Wordpress's Ansible</a>
<ol>
  <table>
    <caption>Vars</caption>
    <thead>
      <tr>
        <th>No</th>
        <th>Var Name</th>
        <th>Value</th>
        <th>Explain</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>1</td>
        <td>git_url</td>
        <td>https://github.com/WordPress/WordPress</td>
        <td>The wordpress git</td>
      </tr> 
      <tr>
        <td>2</td>
        <td>destdir</td>
        <td>/var/www/html/wordress</td>
        <td>Destination directory for installation</td>
      </tr> 
      <tr>
        <td>3</td>
        <td>domain</td>
        <td>ansible host</td>
        <td>Get current lxc's object</td>
      </tr> 
      <tr>
        <td>4</td>
        <td>conf_name_nginx</td>
        <td>app-wp5.9.conf</td>
        <td>File name</td>
      </tr> 
    </tbody>
  </table>
  <img src="https://raw.githubusercontent.com/agisx/Container-LXC-Ubuntu20Server/main/images/tubes/wp/0.PNG">
  <li>Deploy all Wordpress' hosts</li>
  <img src="https://raw.githubusercontent.com/agisx/Container-LXC-Ubuntu20Server/main/images/tubes/wp/all%20hosts.PNG">
  <li>Wordpress's Roles</li> 
  <ol type="a">  
    <li>Install requirement items, add Repository, and clone the Wordpress's git</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/wp/1.1.PNG?raw=true">
    <ul> 
      <li>Delete the files' apt chache</li>
      <li>Install php7 package requirements</li>
      <li>Ignore yes to skip the error from lxc's installed yet package</li>
      <li>Add php repository</li>
    </ul> 
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/wp/1.2.PNG?raw=true">
    <ul> 
      <li>Add key for php packages</li>
      <li>Add php 7 repository</li>
      <li>Install nginx requirements</li>
    </ul>
    <li>Setup the server file</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/wp/1.3.PNG?raw=true">
    <ul> 
      <li>Clone the wp's git</li>
      <li>Copy nginx files template</li>
      <li>Create the symlink</li>
      <li>Copy wordpress's file config</li> 
      <li>Write up the host in hosts file</li>
    </ul> 
    <li>Nginx's config file</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/wp/5.1.PNG?raw=true">
    <li>wordpress's file config</li>
    <img src="https://raw.githubusercontent.com/agisx/Container-LXC-Ubuntu20Server/5aab4f77f4180387c13962728807ae62ff012aed/images/tubes/wp/5.2.PNG">
    <li>The handlers</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/handlers%20wp%20lvl%20yii.PNG?raw=true">
  </ol> 
  
  <table>
    <caption>Vars</caption>
    <thead>
      <tr>
        <th>No</th>
        <th>Var Name</th>
        <th>Value</th>
        <th>Explain</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>1</td>
        <td>full_ip_host</td>
        <td>Full Ip</td>
        <td>Get current lxc's ip</td>
      </tr> 
      <tr>
        <td>2</td>
        <td>ip_host</td>
        <td>Ip</td>
        <td>Split ip into list</td>
      </tr> 
      <tr>
        <td>3</td>
        <td>zone_name</td>
        <td>ip_host[2] + ip_host[1] + ip_host[0] + in-addr</td>
        <td>Set name file</td>
      </tr> 
      <tr>
        <td>4</td>
        <td>last_byte</td>
        <td>ip_host[3]</td>
        <td>File name</td>
      </tr> 
      <tr>
        <td>4</td>
        <td>name_dns</td>
        <td>news</td>
        <td>Set dns name</td>
      </tr> 
    </tbody>
  </table>
  <img src="https://raw.githubusercontent.com/agisx/Container-LXC-Ubuntu20Server/main/images/tubes/dns/0.PNG">
  <li>DNS's Roles</li> 
  <ol type="a">   
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/dns/1.1.PNG?raw=true"> 
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/dns/1.2.PNG?raw=truee"> 
  </ol>
  <li>3.0.10.in-addr.arpa template</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/dns/5.1.PNG?raw=true"> 
  <li>kelompok13.fpsas template</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/dns/5.2.PNG?raw=true"> 
  <li>named.conf.local template</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/dns/5.3.PNG?raw=true"> 
  <li>named.conf.options template</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/dns/5.4.PNG?raw=true"> 
  <li>resolv.conf template</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/dns/5.5.PNG?raw=true"> 
   
  <li>Run Wordpress and dns's ansible</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/wp/run.PNG?raw=true">
  <li>The result</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/wp.PNG?raw=true">
</ol>

<h3>Yii</h3>
<a href="https://github.com/agisx/Container-LXC-Ubuntu20Server/tree/main/images/tubes/yii">Run Yii2's Ansible</a>
<ol>
  <table>
    <caption>Vars</caption>
    <thead>
      <tr>
        <th>No</th>
        <th>Var Name</th>
        <th>Value</th>
        <th>Explain</th>
      </tr>
    </thead>
    <tbody> 
      <tr>
        <td>1</td>
        <td>destdir</td>
        <td>/var/www/html/</td>
        <td>Destination directory for installation</td>
      </tr> 
      <tr>
        <td>2</td>
        <td>domain</td>
        <td>ansible host</td>
        <td>Get current lxc's object</td>
      </tr> 
      <tr>
        <td>3</td>
        <td>conf_name_nginx</td>
        <td>app-yii2.conf</td>
        <td>File name</td>
      </tr> 
    </tbody>
  </table>
  <img src="https://raw.githubusercontent.com/agisx/Container-LXC-Ubuntu20Server/main/images/tubes/yii/0.PNG">
  <li>Deploy all Yii2' hosts</li>
  <img src="https://raw.githubusercontent.com/agisx/Container-LXC-Ubuntu20Server/main/images/tubes/yii/all%20hosts.PNG">
  <li>Yii2's Roles</li> 
  <ol type="a">  
    <li>Install requirement items and add Repository</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/yii/1.1.PNG?raw=true">
    <ul> 
      <li>Delete the files' apt chache</li>
      <li>Install php7 package requirements</li>
      <li>Ignore yes to skip the error from lxc's installed yet package</li>
      <li>Add php repository</li>
    </ul>    
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/yii/1.2.PNG?raw=true">
    <ul> 
      <li>Add key and php repository</li>
      <li>Install nginx requirements</li> 
    </ul>    
    <li>Setup the server file</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/yii/1.3.PNG?raw=true">
    <ul> 
      <li>Create a yii project</li>
      <li>Copy nginx files template</li>
      <li>Copy database file</li>
      <li>Create the symlink</li>  
      <li>Change the permission</li>
    </ul>
    <li>Nginx's config file</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/yii/5.1.PNG?raw=true">
    <li>yii's file config</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/yii/5.2.PNG?raw=true">
    <li>The handlers</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/handlers%20wp%20lvl%20yii.PNG?raw=true">
  </ol>
  <li>Run yii's ansible</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/yii/run.PNG?raw=true">
  <li>The result</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/yii.PNG?raw=true">
</ol>

<h3>Database</h3>
<a href="https://github.com/agisx/Container-LXC-Ubuntu20Server/tree/main/images/tubes/maria">Run Database's Ansible</a>
<ol>
  <table>
    <caption>Vars</caption>
    <thead>
      <tr>
        <th>No</th>
        <th>Var Name</th>
        <th>Value</th>
        <th>Explain</th>
      </tr>
    </thead>
    <tbody> 
      <tr>
        <td>1</td>
        <td>username</td>
        <td>agi</td>
        <td>username</td>
      </tr> 
      <tr>
        <td>2</td>
        <td>password</td>
        <td>password user</td>
        <td>password to root access</td>
      </tr> 
      <tr>
        <td>3</td>
        <td>domain</td>
        <td>lxc_mariadb.dev</td>
        <td>servername</td>
      </tr> 
    </tbody>
  </table>
  <img src="https://raw.githubusercontent.com/agisx/Container-LXC-Ubuntu20Server/main/images/tubes/maria/0.PNG">
  <li>Deploy Mariadb' hosts</li>
  <img src="https://raw.githubusercontent.com/agisx/Container-LXC-Ubuntu20Server/940c27c85b26439c2400164383eb246c2b4e05c5/images/tubes/maria/all%20hosts.PNG">
  <li>Database's Roles</li> 
  <ol type="a">  
    <li>Install requirement items and setup the db's environment</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/maria/1.1.PNG?raw=true">  
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/maria/1.2.PNG?raw=true">  
    <li>Create the databases</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/maria/1.3.PNG?raw=true">  
  </ol>
  <li>Database file config</li> 
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/maria/5.2.PNG?raw=true">      
  <li>Run mariadb's ansible</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/maria/run.PNG?raw=true">     
  <li>The result</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/tubes/maria/mariadb.PNG?raw=true">
</ol>
