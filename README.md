# kibana
version: '2'
services:
  kibana:
    image: docker.elastic.co/kibana/kibana:6.8.4 ## 注意版本一定要根es匹配，否则页面显示异常
    environment:
      SERVER_NAME: pre-bigdata-finmas-kibana
      ELASTICSEARCH_HOSTS: http://es1.data.oriente.internal:9200
    ports:
      - 5601:5601
