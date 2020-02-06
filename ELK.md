https://www.elastic.co/guide/en/logstash/current/advanced-pipeline.html
https://www.elastic.co/guide/en/logstash/current/plugins-inputs-file.html
https://www.elastic.co/guide/en/logstash/7.5/advanced-pipeline.html
https://www.elastic.co/guide/en/logstash/7.5/installing-logstash.html
https://www.elastic.co/guide/en/logstash/7.5/filebeat-modules.html
https://www.elastic.co/guide/en/beats/filebeat/current/filebeat-configuration.html
https://www.elastic.co/guide/en/logstash/current/plugins-filters-mutate.html
https://www.elastic.co/guide/en/logstash/current/plugins-inputs-file.html

bin/logstash -f config/logstash-simple.conf --config.reload.automatic
bin/logstash -f config/logstash-simple.conf --config.reload.automatic
bin/logstash -f config/logstash-simple.conf --config.reload.automatic
.\filebeat.exe -e -c filebeat.yml -d "publish"
