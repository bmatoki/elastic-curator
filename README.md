# Elastic curator

1)install elastic curator at : C:\Program Files\elasticsearch-curator
(click next,next at the installation file.)
2)paste action_file.yml,config.yml file at C:\Program Files\elasticsearch-curator you can locate them under config&action folder
3)put curator.bat at windows scheduler \ with linux run cron job with your settings - recommended to set every 1 hour.

Default settings :
      rollover index every 1 day or every 5gb
      Delete index's older than 60 days or when reach disk space of 300gb
      you can change the settings at action_file.yml before running the bat \ windows scheduler.
        unit_count: NUMBER
        disk_space: NUMBER (GB)

For create rollover alias in your elastic index go to kibana , dev tools
and do a put request to :
http://localhost:9200/%3Clogs-%7Bnow%2Fd%7D-000001%3E

with the values :
```
{
      "aliases": {
        "logs_write": {}
}
```

## Authors

* Boaz Matoki

