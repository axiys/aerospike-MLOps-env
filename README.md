# aerospike-MLOps-env

## Overview (Today)
![alt text](https://github.com/axiys/aerospike-MLOps-env/blob/main/Overview.PNG "Overview")

## Overview (Future)
![alt text](https://github.com/axiys/aerospike-MLOps-env/blob/main/Future State.PNG "Future")

## Installation Notes for Ubuntu 20.x

```
ssh-keygen -t ed25519 -C "xxxx@xxxxxxx.com"
sudo apt-get install xclip
xclip -selection clipboard < ~/.ssh//id_rsa.pub 
ssh -vT git@github.com
git config --global credential.helper store

$ sudo emacs /etc/resolvconf/resolv.conf.d/base
nameserver 8.8.8.8
nameserver 4.4.4.4

$ sudo emacs /etc/hosts
change 127.0.1.1 to 127.0.0.1

$ ubuntu-drivers devices
$ sudo add-apt-repository ppa:graphics-drivers/ppa
$ sudo ubuntu-drivers autoinstall
$ sudo apt install nvidia-dkms-460
$ sudo apt install nvidia-driver-460

OR

sudo apt-add-repository -r ppa:graphics-drivers/ppa
$ sudo apt install linux-modules-nvidia-460-5.4.0-60-generic
$ sudo apt update && sudo apt dist-upgrade.
$ sudo ubuntu-drivers autoinstall again.
$ sudo apt install libnvidia-compute-460:i386 libnvidia-decode-460:i386 libnvidia-encode-460:i386 libnvidia-ifr1-460:i386 libnvidia-fbc1-460:i386 libnvidia-gl-460:i386 

OR

$ sudo apt install libnvidia-compute-460 libnvidia-decode-460 libnvidia-encode-460 libnvidia-ifr1-460 libnvidia-fbc1-460 libnvidia-gl-460 
$ sudo apt install nvidia-kernel-common-460
$ sudo ubuntu-drivers autoinstall again.


OR
sudo apt purge *nvidia* && apt autoremove && apt autoclean 
sudo apt-add-repository -r ppa:graphics-drivers/ppa
sudo apt install nvidia-driver-460
//////////////////////////////////////////
wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2004/x86_64/cuda-ubuntu2004.pin
sudo mv cuda-ubuntu2004.pin /etc/apt/preferences.d/cuda-repository-pin-600
wget https://developer.download.nvidia.com/compute/cuda/11.2.2/local_installers/cuda-repo-ubuntu2004-11-2-local_11.2.2-460.32.03-1_amd64.deb
sudo dpkg -i cuda-repo-ubuntu2004-11-2-local_11.2.2-460.32.03-1_amd64.deb
sudo apt-key add /var/cuda-repo-ubuntu2004-11-2-local/7fa2af80.pub
sudo apt-get update
sudo apt-get -y install cuda



/////////////////////////////////////////
$ sudo apt update
$ sudo apt install emacs-nox gcc g++ bison flex cmake git nodejs npm cppcheck valgrind python3-pip net-tools maven automake autoconf libtool llvm-dev astyle

$ sudo npm install -g npm
$ sudo apt install libcurl4-openssl-dev

$ sudo apt install openjdk-8-jdk openjdk-8-jre
$ sudo apt install openjdk-8-jdk openjdk-8-jre

$ sudo emacs /etc/environment
JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
JRE_HOME=/usr/lib/jvm/java-8-openjdk-amd64/jre
PATH=$PATH:$JAVA_HOME/bin

App Store: Visual Studio Code
Anaconda https://www.anaconda.com/products/individual

wget https://packages.microsoft.com/config/ubuntu/20.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y dotnet-sdk-5.0

sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y aspnetcore-runtime-5.0



////////////////////////////////////

$ sudo emacs /etc/profile

JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
JRE_HOME=/usr/lib/jvm/java-8-openjdk-amd64/jre

SPARK_HOME=/opt/spark
PYSPARK_PYTHON=/usr/bin/python3

PATH=$JAVA_HOME/bin:$SPARK_HOME/bin:$SPARK_HOME/sbin:$PATH

export JAVA_HOME
export JRE_HOME
export SPARK_HOME
export PYSPARK_PYTHON
export PATH

$ sudo ln -s /usr/bin/pip3 /usr/bin/pip
$ sudo ln -s /usr/bin/python3 /usr/bin/python


//////////////////////////////////////////////////////////////////
Docker:
$ sudo apt-get remove docker docker-compose docker-engine docker.io containerd runc
$ sudo apt-get update

$ sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common


$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
$ sudo apt-key fingerprint 0EBFCD88
$ sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"

$ sudo apt-get update
$ sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose

$ sudo groupadd docker
$ sudo usermod -aG docker $USER
$ sudo newgrp docker 

$ docker run hello-world
//////////////////////////////////////////////////////////////////

$ sudo apt autoremove 'intel-*kit'  'intel-oneapi*'

# use wget to fetch the Intel repository public key
$ cd /tmp
$ wget https://apt.repos.intel.com/intel-gpg-keys/GPG-PUB-KEY-INTEL-SW-PRODUCTS.PUB
# add to your apt sources keyring so that archives signed with this key will be trusted.
$ sudo apt-key add GPG-PUB-KEY-INTEL-SW-PRODUCTS.PUB
# remove the public key
rm GPG-PUB-KEY-INTEL-SW-PRODUCTS.PUB

$ echo "deb https://apt.repos.intel.com/oneapi all main" | sudo tee /etc/apt/sources.list.d/oneAPI.list
$ sudo apt update
$ sudo apt install intel-basekit
$ sudo apt install intel-aikit
$ sudo apt install intel-iotkit
$ sudo apt install intel-dlfdkit
$ sudo apt install intel-renderkit
$ sudo apt install intel-hpckit

/////////////////////////////////////////////
$ git config --global credential.helper cache

//////////////////////////////////////////

$ cd ~/Downloads
$ wget https://download.java.net/java/GA/jdk15.0.2/0d1cfde4252546c6931946de8db48ee2/7/GPL/openjdk-15.0.2_linux-x64_bin.tar.gz
$ sudo mkdir -p /usr/java/openjdk
$ cd /usr/java/openjdk
$ sudo tar -xzvf ~/Downloads/openjdk-15.0.2_linux-x64_bin.tar.gz 

$ sudo emacs /etc/profile

# OpenJDK 15
#JAVA_HOME=/usr/java/openjdk/jdk-15
#PATH=$PATH:$HOME/bin:$JAVA_HOME/bin
#export JAVA_HOME
#export PATH

////////////////////////////////
Kafka

$ cd /opt
$ sudo useradd kafka -m
$ sudo passwd kafka
$ sudo adduser kafka
$ sudo addgroup kafka
$ sudo adduser kafka kafka

$ su -l kafka

$ wget https://apache.mirrors.nublue.co.uk/kafka/2.7.0/kafka_2.13-2.7.0.tgz
$ tar -xvf kafka_2.13-2.7.0.tgz

$ sudo emacs /usr/lib/systemd/system/kafka-zookeeper.service

[Unit]
Description=Apache Zookeeper server (Kafka)
Documentation=http://zookeeper.apache.org
Requires=network.target remote-fs.target
After=network.target remote-fs.target

[Service]
Type=simple
User=kafka
Group=kafka
Environment=JAVA_HOME=/usr/java/openjdk/jdk-15
ExecStart=/opt/kafka/bin/zookeeper-server-start.sh /opt/kafka/config/zookeeper.properties
ExecStop=/opt/kafka/bin/zookeeper-server-stop.sh

[Install]
WantedBy=multi-user.target

3. sudo emacs /usr/lib/systemd/system/kafka.service

[Unit]
Description=Apache Kafka server (broker)
Documentation=http://kafka.apache.org/documentation.html
Requires=network.target remote-fs.target
After=network.target remote-fs.target kafka-zookeeper.service

[Service]
Type=simple
User=kafka
Group=kafka
Environment=JAVA_HOME=/usr/java/openjdk/jdk-15
ExecStart=/opt/kafka/bin/kafka-server-start.sh /opt/kafka/config/server.properties
ExecStop=/opt/kafka/bin/kafka-server-stop.sh

[Install]
WantedBy=multi-user.target

$ sudo emacs /opt/kafka/config/server.properties and change the listeners property


5. Reload and start the systemd services

$ sudo systemctl daemon-reload
$ sudo systemctl start kafka-zookeeper.service
$ sudo systemctl start kafka.service

///////////////////

https://www.aerospike.com/download/server/5.5.0.3/
$ wget https://www.aerospike.com/download/server/5.5.0.3/artifact/ubuntu20
$ sudo ./asinstall

/////
PVS Studio
https://www.viva64.com/en/pvs-studio-download/
$ sudo dpkg -i pvs-studio-7.12.46137.116-amd64.deb
$ pvs-studio-analyzer credentials PVS-Studio Free FREE-FREE-FREE-FREE

///////
SSH Server
$ sudo apt install openssh-server
$ sudo ufw allow ssh
$ sudo systemctl status ssh

confluent.io/training

//////////
#https://phoenixnap.com/kb/install-spark-on-ubuntu

$ sudo apt install scala
$ cd /opt/spark
$ wget https://apache.mirrors.nublue.co.uk/spark/spark-3.1.1/spark-3.1.1-bin-hadoop2.7.tgz


Add to
$ sudo emacs /etc/environment
SPARK_HOME=/opt/spark
PATH=$PATH:$SPARK_HOME/bin:$SPARK_HOME/sbin
PYSPARK_PYTHON=/usr/bin/python3


1.

$ sudo useradd spark -m
$ sudo passwd spark
$ sudo adduser spark sudo
$ sudo addgroup spark
$ sudo adduser spark spark


$ sudo emacs /usr/lib/systemd/system/spark.service

[Unit]
Description=Spark service
After=network.target
After=systemd-user-sessions.service
After=network-online.target

[Service]
Type=forking
User=spark
Group=spark
ExecStart=/opt/spark/sbin/start-all.sh
ExecStop=/opt/spark/sbin/stop-all.sh
TimeoutSec=30
Restart=always
RestartSec=30
StartLimitInterval=350
StartLimitBurst=10

[Install]
WantedBy=multi-user.target

2. Reload and start the systemd services

$ sudo systemctl daemon-reload
$ sudo systemctl start spark.service
$ sudo systemctl enable spark.service



3.
$ sudo emacs /usr/lib/systemd/system/spark-slave.service

[Unit]
Description=Spark slave service
After=network.target
After=systemd-user-sessions.service
After=network-online.target
After=spark.service

[Service]
Type=forking
User=spark
Group=spark
ExecStart=/opt/spark/sbin/start-slave.sh spark://user-ThinkCentre-M700:7077
ExecStop=/opt/spark/sbin/stop-slave.sh spark://user-ThinkCentre-M700:7077
TimeoutSec=30
Restart=always
RestartSec=30
StartLimitInterval=350
StartLimitBurst=10

[Install]
WantedBy=multi-user.target

4. Reload and start the systemd services

$ sudo systemctl daemon-reload
$ sudo systemctl start spark-slave.service
$ sudo systemctl enable spark-slave.service

UI: http://127.0.0.1:8080/

///////////////////////////////////
// Benchmark
$ cd ~/dev/tools
$ git clone https://github.com/JonathanMace/tpcds.git
mvn clean package

bin/spark-submit --class edu.brown.cs.systems.tpcds.spark.SparkTPCDSDataGenerator target/spark-workloadgen-4.0.jar
-jar-with-dependencies.jar


cd tpcds

/////

$ echo "deb https://dl.bintray.com/sbt/debian /" | sudo tee -a /etc/apt/sources.list.d/sbt.list
$ curl -sL "https://keyserver.ubuntu.com/pks/lookup?op=get&search=0x2EE0EA64E40A89B84B2DF73499E82A75642AC823" | sudo apt-key add
$ sudo apt-get update
$ sudo apt-get install sbt

///////////////////////
Hadoop

https://archive.apache.org/dist/hadoop/common/
https://dev.to/awwsmm/installing-and-running-hadoop-and-spark-on-ubuntu-18-393h

$ cd /opt/hadoop
$ sudo wget https://www.apache.org/dyn/closer.cgi/hadoop/common/hadoop-3.2.2/hadoop-3.2.2.tar.gz
$ sudo tar -xvf hadoop-3.2.2.tar.gz

$ sudo useradd hadoop -m
$ sudo passwd hadoop
$ sudo adduser hadoop sudo
$ sudo addgroup hadoop
$ sudo adduser hadoop hadoop

1.
$ sudo emacs /usr/lib/systemd/system/hadoop-dfs.service

[Unit]
Description=Hadoop DFS service
After=network.target
After=systemd-user-sessions.service
After=network-online.target

[Service]
Type=forking
User=hadoop
Group=hadoop
Environment=JAVA_HOME=/usr/java/openjdk/jdk-15
Environment=HADOOP_HOME=/opt/hadoop/default
ExecStart=/opt/hadoop/default/sbin/start-dfs.sh
ExecStop=/opt/hadoop/default/sbin/stop-dfs.sh
WorkingDirectory=/opt/hadoop/default
TimeoutSec=30
Restart=always
RestartSec=30
StartLimitInterval=350
StartLimitBurst=10

[Install]
WantedBy=multi-user.target


2.
$ sudo emacs /usr/lib/systemd/system/hadoop-yarn.service

[Unit]
Description=Hadoop YARN service
After=network.target
After=systemd-user-sessions.service
After=network-online.target
After=hadoop-dfs.service

[Service]
Type=forking
User=hadoop
Group=hadoop
Environment=JAVA_HOME=/usr/java/openjdk/jdk-15
Environment=HADOOP_HOME=/opt/hadoop/default
ExecStart=/opt/hadoop/default/sbin/start-yarn.sh
ExecStop=/opt/hadoop/default/sbin/stop-yarn.sh
WorkingDirectory=/opt/hadoop/default
TimeoutSec=30
Restart=always
RestartSec=30
StartLimitInterval=350
StartLimitBurst=10

[Install]
WantedBy=multi-user.target


$ hdfs namenode -format -force

2. Reload and start the systemd services

$ sudo systemctl daemon-reload
$ sudo systemctl start hadoop-dfs.service
$ sudo systemctl start hadoop-yarn.service
$ sudo systemctl enable hadoop-dfs.service
$ sudo systemctl enable hadoop-yarn.service


//////////////////////////////////////////////////////////
Your SSH isn't setup properly

$ ssh-keygen -t rsa -P ""
$ cat $HOME/.ssh/id_rsa.pub >> $HOME/.ssh/authorized_keys
$ ssh localhost



//////
// Confluent kafka
#https://docs.confluent.io/platform/current/installation/installing_cp/deb-ubuntu.html#systemd-ubuntu-debian-install
$ wget -qO - https://packages.confluent.io/deb/6.1/archive.key | sudo apt-key add -
$ sudo add-apt-repository "deb [arch=amd64] https://packages.confluent.io/deb/6.1 stable main"

$ sudo apt-get update && sudo apt-get install confluent-community-2.13

$ sudo systemctl start confluent-zookeeper
$ sudo systemctl start confluent-server
$ sudo systemctl start confluent-kafka
$ sudo systemctl start confluent-control-center
$ sudo systemctl start confluent-kafka-connect
$ sudo systemctl start confluent-kafka-rest
$ sudo systemctl start confluent-ksqldb
$ sudo systemctl start confluent-schema-registry

$ sudo systemctl enable confluent-zookeeper
$ sudo systemctl enable confluent-server
$ sudo systemctl enable confluent-kafka
$ sudo systemctl enable confluent-control-center
$ sudo systemctl enable confluent-kafka-connect
$ sudo systemctl enable confluent-kafka-rest
$ sudo systemctl enable confluent-ksqldb
$ sudo systemctl enable confluent-schema-registry


Test

$ sudo apt install jq
$ curl --silent -X GET http://localhost:7081/subjects | jq

######
sudo apt update
sudo apt install samba
mkdir /home/user/share/

sudo emacs /etc/samba/smb.conf

[user_share]
    comment = Samba on Ubuntu
    path = /home/user/share
    read only = no
    browsable = yes


sudo service smbd restart
sudo ufw allow samba

sudo smbpasswd -a user

#############################
Need features.conf in /etc/aerospike for Spark connector
Github https://github.com/citrusleaf/aerospike-server-enterprise/blob/master/etc/features.conf
$ sudo cp features.conf /etc/aerospike/


/////////
// https://www.aerospike.com/docs/connect/tutorials/spark/notebook.html
// https://github.com/aerospike-examples/interactive-notebooks


$ mkdir -p ~/dev/notebooks/

Create spark-jupyter-install.sh:

sudo pip3 install --upgrade pip
sudo pip3 install jupyter spylon-kernel PySpark findspark numpy pandas matplotlib sklearn

sudo python3 -m spylon_kernel instal
sudo pip3 install spylon-kernel

# should display kernel installed python3 and spylon
jupyter kernelspec list

///////////////////////////////////////////////
// Install PySpark
# https://spark.apache.org/docs/latest/api/python/getting_started/install.html#using-pypi
sudo pip install pyspark[sql]

sudo emacs /etc/profile

PYSPARK_DRIVER_PYTHON=jupyter
PYSPARK_DRIVER_PYTHON_OPTS='notebook'

export PYSPARK_DRIVER_PYTHON
export PYSPARK_DRIVER_PYTHON_OPTS

pyspark

////
Test Aerospike https://github.com/aerospike-examples/interactive-notebooks
#sudo yum install gcc zlib-devel openssl-devel libffi-devel sqlite-devel bzip2-devel bzip2 xz-devel screen wget
sudo apt install zlib1g-dev libssl-dev libffi-dev libsqlite3-dev libbz2-dev liblzma-dev screen wget
sudo pip3 install jupyter PySpark findspark numpy pandas matplotlib sklearn


////

/////////////////////////////////////////
# Java Kernel
# https://github.com/SpencerPark/IJava#installing
mkdir -p ~/dev/tools/jupyter-kernels
cd ~/dev/tools/jupyter-kernels

wget https://github.com/SpencerPark/IJava/releases/download/v1.3.0/ijava-1.3.0.zip
rm -rf ijava
mkdir ijava
cd ijava
unzip ../ijava-1.3.0.zip
sudo python3 install.py --sys-prefix

sudo pip3 install aerospike PyHive
/////////////////////////////////////////////

// https://coding-stream-of-consciousness.com/2018/12/19/centos7-rhel7-services-with-systemd-systemctl-for-dummies-presto-example/

$ mkdir -p /opt/presto
$ wget https://repo1.maven.org/maven2/com/facebook/presto/presto-server/0.248/presto-server-0.248.tar.gz
$ tar -xvf presto-server*gz
$ mv /opt/presto-server-0.248 presto

////
$ sudo mkdir etc
$ sudo emacs etc/config.properties

coordinator=true
node-scheduler.include-coordinator=true
http-server.http.port=9070
query.max-memory=5GB
query.max-memory-per-node=1GB
query.max-total-memory-per-node=2GB
discovery-server.enabled=true
discovery.uri=http://127.0.0.1:9070 


$ sudo emacs etc/jvm.config
-server
-Xmx16G
-XX:+UseG1GC
-XX:G1HeapRegionSize=32M
-XX:+UseGCOverheadLimit
-XX:+ExplicitGCInvokesConcurrent
-XX:+HeapDumpOnOutOfMemoryError
-XX:+ExitOnOutOfMemoryError
-Djdk.attach.allowAttachSelf=true

$ sudo mkdir -p /var/presto/data
$ emacs etc/node.properties
node.environment=production
node.id=ffffffff-ffff-ffff-ffff-ffffffffffff
node.data-dir=/var/presto/data

$ sudo mkdir -p etc/catalog
$ emacs jmx.properties
connector.name=jmx

///

$ sudo mkdir -p /opt/presto/data/var/log
$ sudo emacs run.sh
bin/launcher stop && bin/launcher start && tail -f /opt/presto/data/var/log/server.log
$ chmod 755 run.sh


$ sudo groupadd presto
$ sudo useradd presto -g presto
$ sudo emacs /usr/lib/systemd/system/presto.service

[Unit]
Description=Presto Server

[Service]
Type=forking
User=presto
Group=presto
ExecStart=/opt/presto/bin/launcher start
ExecStop=/opt/presto/bin/launcher stop

[Install]
WantedBy=multi-user.target


$ sudo systemctl daemon-reload
$ sudo systemctl enable presto.service
$ sudo systemctl start presto.service


optional:
connector.name=aerospike
aerospike.hostname=localhost
aerospike.port=3000


Download cli
https://docs.datomic.com/cloud/analytics/analytics-cli.html
$ cd /opt/presto/bin
$ wget https://repo1.maven.org/maven2/io/prestosql/presto-cli/348/presto-cli-348-executable.jar
$ mv presto-cli-348-executable.jar presto
$ chmod +x presto

./presto --server localhost:9070 --catalog hive --schema default
HELP
SHOW CATALOGS;
SHOW SCHEMAS FROM aerospike;
QUIT;
./presto --server localhost:9070 --catalog aerospike --schema test

USE aerospike.test;
presto:test> SHOW TABLES;


////////
Presto AS
// https://github.com/citrusleaf/aerospike-connect-presto

$ cd /tmp
$ wget https://www.aerospike.com/enterprise/download/connectors/aerospike-prestosql/1.0.0/artifact/zip-sql aerospike-prestosql.tgz
$ unzip zip-sql
$ sudo -u presto mkdir -p /opt/presto/plugin/aerospike
$ sudo -u presto cp -r presto-aerospike-1.0.0/*.jar /opt/presto/plugin/aerospike 


https://aerospike.com/docs/connect/access/presto/configuration.html
$ sudo -u presto emacs /opt/presto/etc/catalog/aerospike.properties
connector.name=aerospike
aerospike.hostname=localhost
aerospike.port=3000
aerospike.table-desc-dir=/opt/presto/etc/catalog/schemas/aerospike

$ mkdir -p /opt/presto/etc/catalog/schemas/aerospike
$ cd /opt/presto/etc/catalog/schemas/aerospike
$ emacs test.table1.json
{
 "schemaName": "test",
 "tableName": "table1",
 "columns":[
     {
         "name": "id",
         "type": "varchar",
         "hidden": false
     },
     {
         "name": "age",
         "type": "bigint",
         "hidden": false
     },
     {
         "name": "list",
         "type": "json",
         "hidden": false
     },
     {
         "name": "map",
         "type": "json",
         "hidden": false
     }
 ]
}


$ sudo systemctl restart presto.service


$ emacs /etc/aerospike/aerospike.conf

service {
        cluster-name demo
	...

$ sudo systemctl restart aerospike.service


////
$ cd /opt
$ wget http://h2o-release.s3.amazonaws.com/h2o/rel-zermelo/5/h2o-3.32.0.5.zip
$ unzip h2o-3.32.0.5.zip
$ mv h2o-3.32.0.5 h2o

$ sudo groupadd h2o
$ sudo useradd h2o -g h2o
$ sudo emacs /usr/lib/systemd/system/h2o.service

[Unit]
Description=H2O the optimized HTTP/1, HTTP/2 server
After=syslog.target network.target remote-fs.target nss-lookup.target
 
[Service]
Type=forking
User=h2o
Group=h2o
PIDFile=/var/run/h2o/h2o.pid
ExecStart=java -jar /opt/h2o/h2o.jar
ExecReload=/bin/kill -s HUP $MAINPID
ExecStop=/bin/kill -s QUIT $MAINPID
PrivateTmp=true
 
[Install]
WantedBy=multi-user.target

$ sudo systemctl daemon-reload
$ sudo systemctl enable h2o.service
$ sudo systemctl start h2o.service


#sudo pip install h2o pysparkling

$ cd /opt/h2o
$ wget https://s3.amazonaws.com/h2o-release/sparkling-water/spark-3.0/3.32.0.5-1-3.0/sparkling-water-3.32.0.5-1-3.0.zip
$ export MASTER="local[*]"
$ export JAVA_HOME=/usr/java/openjdk/jdk-15
$ export PATH=$JAVA_HOME/bin:$PATH

$ unzip sparkling-water-3.32.0.5-1-3.0.zip
$ cd sparkling-water-3.32.0.5-1-3.0
$ bin/sparkling-shell --conf "spark.executor.memory=1g"


//////////////////////////////////////////////////////////////////////////////////////////

#./spark-jupyter-version.sh

SPARK_VERSION=3.1.1
HADOOP_VERSION=2.7
PRESTO_VERSION=0.248

# Spark
cd /tmp
rm spark-$SPARK_VERSION-bin-hadoop$HADOOP_VERSION.tgz
wget https://downloads.apache.org/spark/spark-$SPARK_VERSION/spark-$SPARK_VERSION-bin-hadoop$HADOOP_VERSION.tgz
tar xvfz spark-$SPARK_VERSION-bin-hadoop$HADOOP_VERSION.tgz
sudo mv spark-$SPARK_VERSION-bin-hadoop$HADOOP_VERSION /opt/
export SPARK_HOME=/opt/spark-$SPARK_VERSION-bin-hadoop$HADOOP_VERSION

# Presto
# https://prestodb.io/docs/current/installation/deployment.html
cd /tmp
rm aerospike-presto*
wget https://www.aerospike.com/enterprise/download/connectors/aerospike-prestosql/1.0.0/artifact/zip-sql aerospike-prestosql.tgz
mkdir /opt/presto
cd /opt/presto
wget https://repo1.maven.org/maven2/com/facebook/presto/presto-server/0.248/presto-server-$PRESTO_VERSION.tar.gz
tar xvf presto-server-$PRESTO_VERSION.tar.gz

cd presto-server-$PRESTO_VERSION

////
mkdir etc
emacs etc/config.properties

coordinator=true
node-scheduler.include-coordinator=false
http-server.http.port=9080
query.max-memory=50GB
query.max-memory-per-node=1GB
query.max-total-memory-per-node=2GB
discovery-server.enabled=true
discovery.uri=http://192.168.1.35:9080


emacs etc/jvm.config
-server
-Xmx16G
-XX:+UseG1GC
-XX:G1HeapRegionSize=32M
-XX:+UseGCOverheadLimit
-XX:+ExplicitGCInvokesConcurrent
-XX:+HeapDumpOnOutOfMemoryError
-XX:+ExitOnOutOfMemoryError

mkdir -p /var/presto/data
emacs etc/node.properties
node.environment=production
node.id=ffffffff-ffff-ffff-ffff-ffffffffffff
node.data-dir=/var/presto/data

mkdir -p etc/catalog
emacs jmx.properties
connector.name=jmx

///

bin/launcher start && tail -f /var/presto/data/var/log/server.log






///////////////////////////////////////////

create spark-jupyter-run.sh:

SPARK_VERSION=3.1.1
HADOOP_VERSION=2.7

export SPARK_HOME=/opt/spark-${SPARK_VERSION}-bin-hadoop${HADOOP_VERSION}
export PYTHONPATH=$SPARK_HOME/python:$PYTHONPATH
jupyter notebook --no-browser --ip=192.168.1.35 --port=8888 --notebook-dir=~/dev/notebooks

//////////////////////////////////////////////////////////////////

OR

# on your local machine
ssh -L 8888:localhost:8888 user@192.168.1.35

# on remote
cd dev/notebooks
jupyter notebook

///////////////////////////////////////////

Get the URL to view

In spylon-kernel:

[1] %%init_spark
launcher.jars = ["aerospike-spark-assembly-2.7.0.jar"]
launcher.master = "local[*]"

To see if it loads



///////

/////////////////////
// https://www.cyberciti.biz/faq/ubuntu-linux-install-nvidia-driver-latest-proprietary-driver/
$ sudo apt install hwinfo
$ hwinfo --gfxcard --short
$ sudo lshw -C display

//////////////////////////////
// Trino
// https://trino.io/docs/current/installation/deployment.html

cd /opt
$ wget https://repo1.maven.org/maven2/io/trino/trino-server/354/trino-server-354.tar.gz
$ tar -xvf trino-server-354.tar.gz
$ mv trino-server-354 trino

$ adduser presto -g presto
$ cd trino
$ chown -R presto .
$ chgrp -R presto .

$ sudo emacs /usr/lib/systemd/system/trino.service

[Unit]
Description=Tino Server

[Service]
Type=forking
User=presto
Group=presto
Environment=JAVA_HOME=/usr/java/openjdk/jdk-15
Environment=PATH=$JAVA_HOME/bin:$PATH
connector.name=aerospike
aerospike.hostlist=localhost:3000

ExecStart=/opt/trino/bin/launcher start
ExecStop=/opt/trino/bin/launcher stop

[Install]
WantedBy=multi-user.target

$ mkdir etc
$ emacs etc/node.properties

node.environment=production
node.id=ffffffff-ffff-ffff-ffff-ffffffffffff
node.data-dir=/var/trino/data

$ mkdir data
$ emacs etc/jvm.config

-server
-Xmx16G
-XX:-UseBiasedLocking
-XX:+UseG1GC
-XX:G1HeapRegionSize=32M
-XX:+ExplicitGCInvokesConcurrent
-XX:+ExitOnOutOfMemoryError
-XX:+HeapDumpOnOutOfMemoryError
-XX:ReservedCodeCacheSize=512M
-XX:PerMethodRecompilationCutoff=10000
-XX:PerBytecodeRecompilationCutoff=10000
-Djdk.attach.allowAttachSelf=true
-Djdk.nio.maxCachedBufferSize=2000000

$ emacs etc/config.properties

coordinator=true
node-scheduler.include-coordinator=true
http-server.http.port=9071
query.max-memory=5GB
query.max-memory-per-node=1GB
query.max-total-memory-per-node=2GB
discovery-server.enabled=true
discovery.uri=http://127.0.0.1:9071

$ emacs etc/log.properties

io.trino=INFO

$ mkdir etc/catalog
$ emacs etc/catalog/jmx.properties




$ cd /tmp
$ wget https://www.aerospike.com/enterprise/download/connectors/aerospike-prestosql/1.0.0/artifact/zip-sql aerospike-prestosql.tgz
$ unzip zip-sql
$ sudo -u presto mkdir -p /opt/trino/plugin/aerospike
$ sudo -u presto cp -r presto-aerospike-1.0.0/*.jar /opt/trino/plugin/aerospike


https://aerospike.com/docs/connect/access/presto/configuration.html
$ sudo -u presto emacs /opt/trino/etc/catalog/aerospike.properties
connector.name=aerospike
aerospike.hostname=localhost
aerospike.port=3000

$ sudo systemctl daemon-reload
$ sudo systemctl enable trino.service
$ sudo systemctl start trino.service


AS EE building

sudo apt-get install libldap2-dev
```
