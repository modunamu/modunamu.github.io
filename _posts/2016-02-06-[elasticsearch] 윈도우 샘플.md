---
layout: post
title: "2016-02-06-[윈도우] elasticsearch 샘플"
categories: [elasticsearch]
tags: [윈도우, elasticsearch, Logstach, kibana]
description: elasticsearch 샘플.md
---



## Logstach
### card-oracle-elastic.conf(oracle->elastic)
* http://dbtricks.com/?p=308

```
# file: simple-out.conf
input {
    jdbc {
        jdbc_connection_string => "jdbc:oracle:thin:@52.2.171.133:1521/ENMQADB"
        jdbc_user => "ENM_APP"
        jdbc_password => "enmapp"
        #jdbc_validate_connection => "TRUE"
        jdbc_driver_library => "C:\dev\logstash-2.3.2\bin\ojdbc6.jar"
        jdbc_driver_class => "Java::oracle.jdbc.driver.OracleDriver"
        statement => "SELECT dti_wdate, sup_amount, tax_amount, total_amount, sup_com_regno,sup_com_name, sup_emp_name,sup_com_type, sup_com_classify, creation_date from xxsb_dti_nts_main where creation_date > sysdate - 100 "
    }
}
output {
    elasticsearch {
        #protocol => http
        index => "corp-card"
        document_type => "corp-card"
        document_id => "%{uid}"
        hosts => ["127.0.0.1"]
    }
}
```


## Kibana - Sense
### copr-card sample using sense
```
GET corp-card/_search

PUT corp-card
  {
    "mappings" : {
      "corp-card" : {
        "properties" : {
          "dti_wdate" : { "type" : "date" },
          "sup_amount" : { "type" : "integer"},
          "tax_amount" : { "type" : "integer"},
          "total_amount" : { "type" : "integer"},
          
          "sup_com_regno" : { "type" : "string" },
          "sup_com_name" : { "type" : "string" },
          "sup_emp_name" : { "type" : "string" },
          "sup_com_type" : { "type" : "string" },
          "sup_com_classify" : { "type" : "string" },
          "creation_date" : { "type" : "date" }
        }
      }
    }
  }
```



