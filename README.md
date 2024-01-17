# Домашнее задание к занятию «ELK» Бережок А. Fops-16

### При выполнении задания используйте дополнительные ресурсы:
### - [docker-compose elasticsearch + kibana](11-03/docker-compose.yaml);
### - [поднимаем elk в docker](https://www.elastic.co/guide/en/elasticsearch/reference/7.17/docker.html);
### - [поднимаем elk в docker с filebeat и docker-логами](https://www.sarulabs.com/post/5/2019-08-12/sending-docker-logs-to-elasticsearch-and-kibana-with-filebeat.html);
### - [конфигурируем logstash](https://www.elastic.co/guide/en/logstash/7.17/configuration.html);
### - [плагины filter для logstash](https://www.elastic.co/guide/en/logstash/current/filter-plugins.html);
### - [конфигурируем filebeat](https://www.elastic.co/guide/en/beats/libbeat/5.3/config-file-format.html);
### - [привязываем индексы из elastic в kibana](https://www.elastic.co/guide/en/kibana/7.17/index-patterns.html);
### - [как просматривать логи в kibana](https://www.elastic.co/guide/en/kibana/current/discover.html);
### - [решение ошибки increase vm.max_map_count elasticsearch](https://stackoverflow.com/questions/42889241/how-to-increase-vm-max-map-count).

### **Примечание**: если у вас недоступны официальные образы, можете найти альтернативные варианты в DockerHub, например, [такой](https://hub.docker.com/layers/bitnami/elasticsearch/7.17.13/images/sha256-8084adf6fa1cf24368337d7f62292081db721f4f05dcb01561a7c7e66806cc41?context=explore).

## Задание 1. Elasticsearch 

### Установите и запустите Elasticsearch, после чего поменяйте параметр cluster_name на случайный. 
### 
### *Приведите скриншот команды 'curl -X GET 'localhost:9200/_cluster/health?pretty', сделанной на сервере с установленным Elasticsearch. Где будет виден нестандартный cluster_name*.
### Не очень понял про случайный кластер, поставил просто свой 'elastic_hw_netology'. 
### Еще установил 8 версию Elastica, наверно зря, там какие-то вечные проблемы с паролями и аутентификацией
### ![](https://github.com/Berezhok/hw_ELK/blob/main/img/status.png)
### ![](https://github.com/Berezhok/hw_ELK/blob/main/img/claster.png)
### 
### 
### 
### 
## Задание 2. Kibana

### Установите и запустите Kibana.
### 
### *Приведите скриншот интерфейса Kibana на странице http://<ip вашего сервера>:5601/app/dev_tools#/console, где будет выполнен запрос GET /_cluster/health?pretty*.
### ![](https://github.com/Berezhok/hw_ELK/blob/main/img/kibanastatus.png)
### ![](https://github.com/Berezhok/hw_ELK/blob/main/img/kibana.png) 
### ![](https://github.com/Berezhok/hw_ELK/blob/main/img/get_response.png)
### 
### 
### 
## Задание 3. Logstash

### Установите и запустите Logstash и Nginx. С помощью Logstash отправьте access-лог Nginx в Elasticsearch. 
### 
### *Приведите скриншот интерфейса Kibana, на котором видны логи Nginx.*
### Логи видны в Kibana
### ![](https://github.com/Berezhok/hw_ELK/blob/main/img/nginxKibana.png) 
## Задание 4. Filebeat. 
### 
### Установите и запустите Filebeat. Переключите поставку логов Nginx с Logstash на Filebeat. 
### *Приведите скриншот интерфейса Kibana, на котором видны логи Nginx, которые были отправлены через Filebeat.*
### Filebeat установил. Настроил конфигурационные файлы. В файле logstash.conf ввел новое название для индекса (nginx-index-filebeat) для визуального 
### понимания. Несколько раз по-curl-ил, пообновлял вебсервер. Получил запись в access.log, они также отобразились в kibana
### ![](https://github.com/Berezhok/hw_ELK/blob/main/img/indexFilebeat.png)
### ![](https://github.com/Berezhok/hw_ELK/blob/main/img/kibana_beat.png)
### Еще раз огромное спасибо Марату за помощь! 🤝 Без помощи, так бы и сидел на этом задании. 🤣
###
###
###