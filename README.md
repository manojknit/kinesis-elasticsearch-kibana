# Real-time log monitoring using Kinesis Firehose, Elastic Search and Kibana

Deployement steps:
1. Zip all the files and upload to S3
2. Set up Ubuntu EC2
3. Make sure python version 3 is installed.
4. Make sure pip3 is installed

5. Create project folder. After you enter the parent folder.
6. Download zip file from s3
7. unzip file.zip.  (sudo apt-get install unzip)
8. Install all the required python modules by using the following command
9. pip3 install requirements.txt
10. Run
$ python Webdata_generator_retailer.py


Reference:
[Kinesis Firehose & Elastic Search](https://www.youtube.com/watch?v=_tIvv8h-c44)