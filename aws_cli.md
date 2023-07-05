# AWS CLI

As much as we can create buckets using the AWS interface, we can also do this using the AWS CLI.

The AWS CLI itself uses **Python!**

## Installing AWS CLI
A folder in _tech_241_ has been manually created called _s3_buckets_.

Using the GitBash terminal, `cd` into the folder.
```commandline
cd s3_buckets
```
Use the `pip` command to install AWS CLI.
```commandline
pip install awscli
```
Now that AWSCLI is installed, we need to sync up to our area and permissions of AWS. To do this, we run
```commandline
aws configure
```
Then personal IDs are entered, and we can get started!

Once it's configured, we can run `aws s3 ls` to see the list of all the buckets.

## Creating a bucket using AWS CLI
We need to specify `s3` as the service we want to use, and use the command `mb` (make bucket) and where we want to make it.
```commandline
aws s3 mb s3://[name we want to give the bucket] --region [the region]
```
The region isn't always needed in the command, but it's best practice.

Once the bucket's been created it can be viewed in the AWS console.

## Upload file to bucket
Create a test file called textfile.txt in the s3_buckets folder.
```commandline
aws s3 cp testfile.txt s3://tech241-deanne-bucket

```
## Download file from bucket
```commandline
aws s3 sync s3://tech241-deanne-bucket s3_download
```

## Delete from bucket
```commandline
aws s3 rm s3://tech241-deanne-bucket/testfile.txt
```

## Delete bucket
```commandline
aws s3 rb s3://tech241-deanne-bucket
```