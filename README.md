# CDC with MySql

## What is CDC?
>Change data capture (CDC) is the process of recognising when data has been changed in a source system so a downstream process or system can action that change.
## Push vs Pull
>There are two main ways for change data capture systems to operate. Either the source system pushes changes to the target, or the target periodically polls the source and pulls the changed data.
## CDC Mechanisms:

- Time/Version/Status on rows
- Triggers on tables
- Event programming / Pub-Sub pattern
- Log/change scanning
- Binlog replication

## Open source tools:
- [Debezium](https://debezium.io/)
- [Maxwell’s daemon](https://maxwells-daemon.io/)
- [SpinalTap](https://github.com/airbnb/SpinalTap) from AirBnb
- [MySQL Streamer](https://github.com/Yelp/mysql_streamer) from Yelp
- DBLog (Not open source yet) from Netflix

## Binlog may not be enabled by default. To enable it the update MySQL configuration:
```
server-id         = 42
log_bin           = mysql-bin
binlog_format     = ROW
expire_logs_days  = 10
# define `binlog_row_image` for MySQL 5.6 or higher,
# leave it out for earlier releases
binlog_row_image  = FULL
```

---
## Useful Links:
- Netflix Technology Blog: [DBLog: A Generic Change-Data-Capture Framework](https://netflixtechblog.com/dblog-a-generic-change-data-capture-framework-69351fb9099b)
- DataCater: [MySQL Change Data Capture (CDC): The Complete Guide](https://datacater.io/blog/2021-08-25/mysql-cdc-complete-guide.html#cdc-binlog)
