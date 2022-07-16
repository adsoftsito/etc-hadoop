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
11. wget http://apache.cs.utah.edu/hadoop/common/current/hadoop-3.3.3.tar.gz
12. tar -xzf hadoop-3.3.3.tar.gz
13. mv hadoop-3.3.3 hadoop
