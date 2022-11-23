## Database configuration
- Create database
- Create table

```
CREATE TABLE queries ( 
  app String,
  query String,  
  label String,
  name String,
  timestamp DateTime64(9),
  value Float64,
  version UInt32
) ENGINE = ReplacingMergeTree(version)
PARTITION BY toYYYYMM(timestamp)
ORDER BY (app, query, label, name, timestamp);
```
