# Real-time log monitoring using Kinesis Firehose, Elastic Search and Kibana

#### Architecture Diagram:
![System Architecture](https://github.com/manojknit/kinesis-elasticsearch-kibana/raw/master/images/kinesiskibana.png)

#### Deployment steps:
1. Create AWS infrastructure as in Architecture
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