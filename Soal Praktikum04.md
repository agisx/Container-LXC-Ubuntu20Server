<h1>Analisis Load Balancing</h1>
<ol>
  <h2>Setup config file vm local</h2>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum04/3.PNG?raw=true">  
  <h2>Setup all containers on vm local</h2>
  <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum04/1.PNG?raw=true"> 
  <ol>
    <h3>Test without load balancer</h3>
    <li>50 users</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum04/1.1.PNG?raw=true">  
    <li>100 users</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum04/1.2.PNG?raw=true">  
    <li>150 users</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum04/1.3.PNG?raw=true">  
  </ol>
  <ol>
    <h3>Test with load balancer</h3>
    <li>50 users</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum04/2.1.PNG?raw=true">  
    <li>100 users</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum04/2.2.PNG?raw=true">  
    <li>150 users</li>
    <img src="https://github.com/agisx/Container-LXC-Ubuntu20Server/blob/main/images/Soal%20Praktikum04/2.3.PNG?raw=true">  
  </ol>
</ol>
<ol>
  <li>50 users</li>
  AVG throughput without load balancer is 5.25/sec meanwhile with load balancer we got 36/sec, that has been increase as well as received and sent
  <li>100 users</li>
  AVG throughput without load balancer is 29/sec meanwhile with load balancer we got 42.25/sec, that has been increase as well as received and sent
  <li>150 users</li>
  AVG throughput without load balancer is 36.25/sec meanwhile with load balancer we got 42.25/sec, that has been increase as well as received and sent
</ol>
