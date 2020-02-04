Install Java 8 

> yum install -y java-1.8.0-openjdk

Import GPG Key 

> rpm --import https://artifacts.elastic.co/GPG-KEY-elasticsearch

Create Yum repository 

cat >>/etc/yum.repos.d/elk.repo<<EOF 
[ELK-6.x] 
name=ELK repository for 6.x packages 
baseurl=https://artifacts.elastic.co/packages/6.x/yum 
gpgcheck=1 
gpgkey=https://artifacts.elastic.co/GPG-KEY-elasticsearch 
enabled=1 
autorefresh=1 
type=rpm-md 
EOF


Install Elasticsearch 

> yum install -y elasticsearch

Enable and start elasticsearch service 

> systemctl daemon-reload 
> systemctl enable elasticsearch 
> systemctl start elasticsearch

Install kibana

> yum install -y kibana

Enable and start kibana service 

> systemctl daemon-reload 
> systemctl enable kibana 
> systemctl start kibana

Install Nginx 

> yum install -y epel-release 
> yum install -y nginx

Enable and start nginx service 

> systemctl enable nginx 
> systemctl start nginx

Install logstash 

> yum install -y logstash


