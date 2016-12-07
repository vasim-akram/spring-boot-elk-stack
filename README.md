# spring-boot-elk-stack
Spring-boot with ELK stack.

There are following steps for ELK stack installation and configuration -

Elasticsearch -
     
     curl -O https://download.elasticsearch.org/elasticsearch/elasticsearch/elasticsearch-1.1.1.tar.gz
     tar zxvf elasticsearch-1.7.1.tar.gz
     ./elasticsearch-1.7.1/bin/elasticsearch == to start
     
Kibana -

     curl -O https://download.elasticsearch.org/logstash/logstash/logstash-1.4.2.tar.gz
     tar zxvf logstash-1.4.2.tar.gz
     
Logstash -

     curl -O https://download.elasticsearch.org/logstash/logstash/logstash-1.4.2.tar.gz
     tar zxvf logstash-1.4.2.tar.gz
     ./logstash-1.4.2/bin/logstash agent -v -f logstash-spring-boot.conf == to start
