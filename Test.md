### Log SQL queries and parameters in Hibernate

```
# basic log level for all messages
logging.level.org.hibernate=info

# SQL statements and parameters
logging.level.org.hibernate.SQL=debug
logging.level.org.hibernate.orm.jdbc.bind=trace

# Statistics and slow queries
logging.level.org.hibernate.stat=debug
logging.level.org.hibernate.SQL_SLOW=info

# 2nd Level Cache
logging.level.org.hibernate.cache=debug
```