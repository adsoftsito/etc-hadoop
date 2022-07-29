# config hadoop

1. sudo yum -y update
2. sudo yum install java-1.8.0-openjdk
3. sudo yum install java-1.8.0-openjdk-devel.x86_64
4. sudo hostnamectl set-hostname master/node1/node2
5. sudo vi /etc/hosts
   - 74.208.139.248 master
   - 74.208.139.114 node1
   - 74.208.139.115 node2
6. Only on master: 
   - ssh-keygen -b 4096
   - cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
   - chmod 600  ~/.ssh/authorized_keys 
   - for each node
   -    scp .ssh/id_rsa.pub hadoop@nodeX:.ssh/master.pub
   -    ssh hadoop@nodeX
   -    cat ~/.ssh/master.pub >> ~/.ssh/authorized_keys
   -    exit
   -    ssh nodeX
   -    exit

9. cd
11. 
12. Install hadoop on master and each node
13. 
14. wget http://apache.cs.utah.edu/hadoop/common/current/hadoop-3.3.3.tar.gz
15. tar -xzf hadoop-3.3.3.tar.gz
16. mv hadoop-3.3.3 hadoop

Configure

18. sudo vi .bash_profile
- PATH=/home/hadoop/hadoop/bin:/home/hadoop/hadoop/sbin:$PATH
19. sudo vi .bashrc
-  export HADOOP_HOME=/home/hadoop/hadoop
-  export PATH=${PATH}:${HADOOP_HOME}/bin:${HADOOP_HOME}/sbin


Install hadoop

19. sudo yum install git
20. git clone git clone https://github.com/adsoftsito/etc-hadoop.git
21. cp etc-hadoop/* hadoop/etc/hadoop/
    
Copy config to nodes

22. scp ~/hadoop/etc/hadoop/* nodeX:/home/hadoop/hadoop/etc/hadoop/;

Format HDFS

23. hdfs namenode -format
24. start-dfs.sh /  stop-dfs.sh
25. jps
26. hdfs dfsadmin -report

Test hadoop UI

27. master:9000 / xx.xx.xx.xx:9000

Start hadoop

**The Cauchy-Schwarz Inequality**
$$\left( \sum_{k=1}^n a_k b_k \right)^2 \leq \left( \sum_{k=1}^n a_k^2 \right) \left( \sum_{k=1}^n b_k^2 \right)$$

