# Real-time log monitoring using Kinesis Firehose, Elastic Search and Kibana

#### Architecture Diagram:
![System Architecture](https://github.com/manojknit/kinesis-elasticsearch-kibana/raw/master/images/kinesiskibana.png)

#### Deployment steps:
1. Create AWS infrastructure as in Architecture
   - Query for Kinesis Analytics
  ```
-- ** Continuous Filter ** 
-- Performs a continuous filter based on a WHERE condition.
--          .----------.   .----------.   .----------.              
--          |  SOURCE  |   |  INSERT  |   |  DESTIN. |              
-- Source-->|  STREAM  |-->| & SELECT |-->|  STREAM  |-->Destination
--          |          |   |  (PUMP)  |   |          |              
--          '----------'   '----------'   '----------'               
-- STREAM (in-application): a continuously updated entity that you can SELECT from and INSERT into like a TABLE
-- PUMP: an entity used to continuously 'SELECT ... FROM' a source STREAM, and INSERT SQL results into an output STREAM
-- Create output stream, which can be used to send to a destination
create or replace stream "destination_sql_stream" 
(
CUSTOMER_ID INTEGER, 
IP_ADDRESS VARCHAR(16), 
DEVICE_TYPE VARCHAR(8),
ROUTER_MAC_ADDRESS VARCHAR(32),
DEVICE_NAME VARCHAR(16),
IP_BROWSER VARCHAR(16),
WEBSITE_URL VARCHAR(256),
APP_NAME VARCHAR(8),
IS_APP_FLAG VARCHAR(4),
IS_DOWNLOADED_FLAG VARCHAR(4),
DATA_SIZE INTEGER,
IS_LIVE_STREAMING VARCHAR(4),
COL_DATE VARCHAR(16),
COL_TIME VARCHAR(32)
);

create or replace pump "stream_pump" as  
INSERT into "destination_sql_stream"
select  
"customer_id",
"ip_address",
"device_type",
"router_mac_address",
"device_name",
"ip_browser",
"website_url",
"app_name",
"is_app_flag",
"is_downloaded_flag",
"data_size",
"is_live_streaming",
"COL_date",
"COL_time" 
from "SOURCE_SQL_STREAM_001";
```
2. Zip all the files and upload to S3
3. Set up Ubuntu EC2
4. Make sure python version 3 is installed.
5. Make sure pip3 is installed

6. Create project folder. After you enter the parent folder.
7. Download zip file from s3
8. unzip file.zip.  (sudo apt-get install unzip)
9. Install all the required python modules by using the following command
10. pip3 install requirements.txt
11. Run
```
$ python Webdata_generator_retailer.py
```


#### Reference:
[Kinesis Firehose & Elastic Search](https://www.youtube.com/watch?v=_tIvv8h-c44)
