Deployement steps:
Zip all the files and upload to S3
Set up Ubuntu EC2 
Make sure python version 3 is installed.
Make sure pip3 is installed

Create project folder. After you enter the parent folder.
Download zip file from s3
unzip file.zip.  (sudo apt-get install unzip)
Install all the required python modules by using the following command
pip3 install requirements.txt
Run
$ python Webdata_generator_retailer.py
