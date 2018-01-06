---
layout: post
title: "[윈도우] elasticsearch Logstach 설치"
categories: [elasticsearch]
tags: [윈도우, elasticsearch, Logstach, install]
description: elasticsearch에서 사용할 Logstach 설치
---


### Logstach 다운로드
```
https://www.elastic.co/products/logstash
```

### Logstach 압축해제
```
C:\dev\logstash-2.3.2
```

### Logstach JDBC drivers 
```
C:\dev\logstash-2.3.2\bin>plugin.bat install logstash-input-jdbc
"The use of bin/plugin is deprecated and will be removed in a feature release. P
lease use bin/logstash-plugin."
io/console not supported; tty will not be manipulated
Validating logstash-input-jdbc
Installing logstash-input-jdbc
Installation successful
```

### Oracle Jdbc Driver
```
http://www.oracle.com/technetwork/database/enterprise-edition/jdbc-111060-084321.html
```


### simple-out.conf(oracle->stdout)
* https://www.elastic.co/blog/logstash-jdbc-input-plugin

```
# file: simple-out.conf
input {
    jdbc {
        jdbc_connection_string => "jdbc:oracle:thin:@127.0.0.1:1521/QADB"
        jdbc_user => "QA_APP"
        jdbc_password => "QA_APP"
        #jdbc_validate_connection => "TRUE"
        jdbc_driver_library => "C:\dev\logstash-2.3.2\bin\ojdbc6.jar"
        jdbc_driver_class => "Java::oracle.jdbc.driver.OracleDriver"
        statement => "SELECT * from test where creation_date > sysdate - 100 "
    }
}
output {
    stdout { codec => json_lines }
}
```

### card-oracle-elastic.conf(oracle->elastic)
* http://dbtricks.com/?p=308

```
# file: simple-out.conf
input {
    jdbc {
        jdbc_connection_string => "jdbc:oracle:thin:@127.0.0.1:1521/QADB"
        jdbc_user => "QA_APP"
        jdbc_password => "QA_APP"
        #jdbc_validate_connection => "TRUE"
        jdbc_driver_library => "C:\dev\logstash-2.3.2\bin\ojdbc6.jar"
        jdbc_driver_class => "Java::oracle.jdbc.driver.OracleDriver"
        statement => "SELECT * from test where creation_date > sysdate - 100 "
    }
}
output {
    elasticsearch {
        #protocol => http
        index => "contacts"
        document_type => "contact"
        document_id => "%{uid}"
        host => "ES_NODE_HOST"
    }
}
```


### Logstach 실행
```
C:\dev\logstash-2.3.2\bin>logstash.bat agent -f simple-out.conf
```



## conf 모음

### server 상태
* http://rea1man.tistory.com/entry/ELK-elasticsearch-logstash-kibana-%EC%84%A4%EC%B9%98-%EB%B0%8F-%EC%82%AC%EC%9A%A9

```
input {
  exec {
    command => "free | grep buffers/cache | awk '{print int($3/($3+$4)*100)}'"
    interval => "5"
    type => "mem"
  }
  exec {
    command => "cat /proc/stat | grep 'cpu ' | awk '{print int(($2+$3+$4)/($2+$3+$4+$5)*100)}'"
    interval => "5"
    type => "cpu"
  }
  exec {
    command => "df -k | grep /was | awk '{print ($5*1)}'"
    interval => "5"
    type => "hdd"
  }
}
filter {
  mutate {
    convert => ["message", "integer"]
  }
}
output {
  elasticsearch{
        cluster => "kibana_cluster"
        node_name => "kibana_node"
        protocol => "node"
        host => "[elasticsearch가 설치된 ip 주소]"
        index => "server-status-%{+YYYY.MM.dd}"
  }
}
```

### file -> elastic
```
input {
  file {
    codec => json
    path => "<git project path>/elastic-demo/data/*.log"
  }
}

filter{
  mutate {
    remove_field => [ "@version", "@timestamp", "host", "path" ]
  }
}

output{
  elasticsearch{
    hosts => ["127.0.0.1"]
    index => "seoul-metro-2014"
    document_type => "seoul-metro"
#    user => "<user>"
#    password => "<password>"
  }
}
```

