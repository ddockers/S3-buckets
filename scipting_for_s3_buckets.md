# Scripting for S3 Buckets

First thing to do is import boto3 library
```
import boto3
```

Then set up an s3 connection
```
s3 = boto3.client("s3")
```

## Creating a bucket
Then create a bucket in eu-west-1 region
```
bucket_name = s3.create_bucket(Bucket= "tech241-deanne-python-bucket", CreateBucketConfiguration={"LocationConstraint":"eu-west-1"})
```

Then print bucket name
```
print(bucket_name)
```
## Uploading to bucket
```
s3 = boto3.client("s3")
```
```commandline
bucketCont = s3.upload_file("testFile.txt", "tech241-iveta-py-bucket", "uploadedFile.txt")
```
```commandline
print(bucketCont)
```

## Download from bucket
```commandline
import boto3

# set the s3 connection
s3 = boto3.client("s3")

# download the file
download_file = s3.download_file("tech241-deanne-python-bucket", "testfile.txt", "hasitworked.txt")

print(s3.download_file)
```
### Delete from bucket
```commandline
# Import boto3
import boto3

s3 = boto3.client("s3")

delete_file = s3.delete_object(Bucket="tech241-deanne-python-bucket", Key="testfile.txt")
```
## Delete bucket
```commandline
import boto3

s3 = boto3.resource("s3")

bucket = s3.Bucket("tech241-deanne-python-bucket")
response = bucket.delete()

print(response)
```