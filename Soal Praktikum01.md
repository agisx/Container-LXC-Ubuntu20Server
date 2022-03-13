<ol type="1">  
  <li>Rename ubuntu_php5.6 to ubuntu_landing</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum01/1.1.%20Rename%20Container%20Tanpa%20Clone.PNG?raw=true" alt="">
  <br>
  <ol type="a">  
    <li>type for the command lxc-copy -R -n ubuntu_php5.6 -N ubuntu_landing</li>
  </ol>
  <br>
  <li>Install lxc debian 9</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum01/0.1%20Debian%209%20info.PNG?raw=true" alt="">
  <ol type="a">  
    <li>Make a Container</li>
    <li>Install nginx</li>
    <li>Check the os container</li>
  </ol>
  <br>
  <li>Setup and configure container lxc debian</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum01/2.1.%20Config,%20Folder,%20and%20File.PNG?raw=true" alt="">
  <br>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum01/2.3.%20Folder%20root%20page%20Debian%209.PNG?raw=true" alt="">
  <br>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum01/2.5.%20Curl%20Debian%209%20APP%20PHP5.PNG?raw=true" alt="">
  <ol type="a">  
    <li>Create a config file</li>
    <li>Create a symlink in sites-enabled</li>
    <li>Create a root page and index.html folder</li>
    <li>Add server in the hosts file</li>
    <li>Check it with curl</li>
  </ol>
  <br>
  <li>Setup container lxc landing</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum01/4.1.%20Config,%20Folder,%20and%20File.PNG?raw=true" alt="">
  <br>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum01/4.3.%20Folder%20root%20page%20Ubuntu%20Landing.PNG?raw=true" alt="">
  <br>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum01/4.5.%20Curl%20Ubuntu%20Landing%20page.PNG?raw=true" alt="">
  <ol type="a">  
    <li>Create a config file</li>
    <li>Create a symlink in sites-enabled</li>
    <li>Create a root page and index.html folder</li>
    <li>Add server in hosts file</li>
    <li>Check it with curl</li>
  </ol>
  <br>
  <li>Set lxc landing auto start</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum01/7.1.%20Auto%20start%20on%20landing%20page.PNG?raw=true" alt="">
  <ol type="a">  
    <li>enter into the directory /var/lib/lxc/ubuntu_landing</li>
    <li>nano config</li>
    <li>Add lxc.auto.start = 1</li>
    <li>Restart the lxc</li> 
  </ol>
  <br>
  <li>Setup hosts file</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum01/5.%20Host%20file%20in%20vm.PNG?raw=true" alt="">
  <br>
  <li>See in your browser if it works (vm.local/blog, vm.local/app, vm.local)</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum01/6.1.%20Check%20in%20windws%20browser.PNG?raw=true" alt="">
  <br>
  <li>Analysis</li>
  <ul>  
    <li><strong>Why for php5.6's needs cannot use the ubuntu 16.04, so the os need to be changed to debian 9?</strong></li>
    Ubuntu 16.04 has entered the EoSS where standart support has ended while debian 9 will end at 2022. Ubuntu 16.04 will be a paid version in ESM program (Extended Security Maintenance) by Ubuntu. While the package software of Ubuntu 16.04 is impossible to developed, therefore it will be a paid software. 
  <br>
    <li><strong>Why use LXC virtualization on a website scheme that will be developed?</strong></li>
    in order to be able to divide the service into several operating system into several different os advantages. That's why the application can run by encapsulation or encased according to the purpose of the application. 
  <br>
    <li><strong>What's the meaning of Proxy Server? why vm.local can be assumed to be a Proxy Server?</strong></li> 
   Proxy Server is a system for access a network using an ip Proxy Server. vm.local can be assumed as a Proxy Server because vm.local's just a bridge to proceed to the container app. So we can access the container as vm.local.
  </ul>
</ol>
