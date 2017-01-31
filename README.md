# spring-boot-elk-stack
Spring-boot with ELK stack.

#####There are following steps for ELK stack installation and configuration -

######Elasticsearch -
     
     curl -O https://download.elasticsearch.org/elasticsearch/elasticsearch/elasticsearch-1.1.1.tar.gz
     tar zxvf elasticsearch-1.7.1.tar.gz
     ./elasticsearch-1.7.1/bin/elasticsearch ==> to start
     
######Kibana -

     echo "deb http://packages.elastic.co/kibana/4.4/debian stable main" | sudo tee -a /etc/apt/sources.list.d/kibana-4.4.x.list
     sudo apt-get update
     sudo apt-get -y install kibana
     sudo vi /opt/kibana/config/kibana.yml ==> open and config 
     server.host: "localhost"
     service kibana4 start ==> to start in ubuntu
     http://localhost:5601
######Logstash -

     curl -O https://download.elasticsearch.org/logstash/logstash/logstash-1.4.2.tar.gz
     tar zxvf logstash-1.4.2.tar.gz
     ./logstash-1.4.2/bin/logstash agent -v -f logstash-spring-boot.conf ==> to start
     
######Log parser file (logstash-spring-boot.conf)
  ```
     input {
       file {
         path =>  [ "/home/vasimakram/Documents/app-logs-express/node-log.log" ]
         start_position => "beginning"
         sincedb_path => "/home/vasimakram/inventum/logs/dbfile6"
         codec =>   json {
           charset => "UTF-8"
         }
       }

   }

     output {
       stdout { codec => rubydebug }
       elasticsearch { host => "localhost" }
    }

     filter {
       json {
         source => "message"
       }
     }
```

