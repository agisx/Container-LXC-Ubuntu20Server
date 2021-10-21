<ol type="1">  
  <li>Rename ubuntu_php5.6</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum01/1.1.%20Rename%20Container%20Tanpa%20Clone.PNG?raw=true" alt="">
  <br>
  <ol type="a">  
    <li>command lxc-copy -R -n ubuntu_php5.6 -N ubuntu_landing</li>
  </ol>
  <br>
  <li>Install lxc debian 9</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum01/0.1%20Debian%209%20info.PNG?raw=true" alt="">
  <ol type="a">  
    <li>Membuat Container</li>
    <li>Install nginx</li>
    <li>Check os kontainer</li>
  </ol>
  <br>
  <li>Setup container lxc debian</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum01/2.1.%20Config,%20Folder,%20and%20File.PNG?raw=true" alt="">
  <br>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum01/2.3.%20Folder%20root%20page%20Debian%209.PNG?raw=true" alt="">
  <br>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum01/2.5.%20Curl%20Debian%209%20APP%20PHP5.PNG?raw=true" alt="">
  <ol type="a">  
    <li>Membuat file config</li>
    <li>Membuat symlink di sites-enabled</li>
    <li>Membuat folder root page dan index.html</li>
    <li>Add server di hosts file</li>
    <li>Cek dengan curl</li>
  </ol>
  <br>
  <li>Setup container lxc landing</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum01/4.1.%20Config,%20Folder,%20and%20File.PNG?raw=true" alt="">
  <br>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum01/4.3.%20Folder%20root%20page%20Ubuntu%20Landing.PNG?raw=true" alt="">
  <br>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum01/4.5.%20Curl%20Ubuntu%20Landing%20page.PNG?raw=true" alt="">
  <ol type="a">  
    <li>Membuat file config</li>
    <li>Membuat symlink di sites-enabled</li>
    <li>Membuat folder root page dan index.html</li>
    <li>Add server di hosts file</li>
    <li>Cek dengan curl</li>
  </ol>
  <br>
  <li>Set lxc landing auto start</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum01/7.1.%20Auto%20start%20on%20landing%20page.PNG?raw=true" alt="">
  <ol type="a">  
    <li>Masuk directory /var/lib/lxc/ubuntu_landing</li>
    <li>nano config</li>
    <li>Tambah lxc.auto.start = 1</li>
    <li>Restart lxc</li> 
  </ol>
  <br>
  <li>Setup hosts file</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum01/5.%20Host%20file%20in%20vm.PNG?raw=true" alt="">
  <br>
  <li>Browser view windows</li>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum01/6.1.%20Check%20in%20windws%20browser.PNG?raw=true" alt="">
  <br>
  <li>Analisa</li>
  <ul>  
    <li><strong>Mengapa untuk kebutuhan php5.6 tidak bisa menggunakan ubuntu 16.04, sehingga perlu diganti os ke debian 9?</strong></li>
    Ubuntu 16.04 telah memasuki EoSS dimana telah berakhir standart support sedangkan debian 9 akan berakhir pada tahun 2022. Ubuntu 16.04 akan menjadi versi berbayar dalam program ESM(Extended Security Maintenance
) oleh ubuntu. Sedangkan paket software ubuntu 16.04 mustahil untuk dikembangkan, maka dari itu akan dijadikan software berbayar. 
  <br>
    <li><strong>Kenapa harus menggunakan virtualisasi LXC pada skema website yang akan didevelop?</strong></li>
    Agar dapat membagi-bagi pelayanan ke beberapa sistem operasi dengan kelebihan os yang berbeda-beda. Maka dari itu aplikasi dapat berjalan secara enkapsulasi atau terbungkus sesuai tujuan aplikasi.
  <br>
    <li><strong>Apa yang dimaksud dengan proxy server? kenapa vm.local bisa kita anggap sebagai proxy server?</strong></li> 
    Proxy server adalah suatu sistem untuk mengakses suatu jaringan menggunakan ip proxy server. vm.local dapat dikatakan proxy server karena vm.local hanya sebagai jembatan untuk dilanjutkan ke app kontainernya. Jadi kita mengakses kontainer sebagai vm.local.
  </ul>
</ol>
<table>
  <caption>Anggota Kelompok</caption>
  <thead>
    <tr>
      <th>Nama</th>
      <th>NIM</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Agi Lobita Japtara Martadinata</td>
      <td>1202190031</td>
    </tr>
    <tr>
      <td>Dewa Nusantara Murdoko Putra</td>
      <td>1202190053</td>
    </tr>
  </tbody>
</table>
