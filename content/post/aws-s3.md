+++
title = "AWS s3"
description = "This page shows some basic commands used in s3"
tags = [
    "aws",
    "s3",
    "aws-s3",
]
date = "2020-09-06"
categories = [
    "aws",
    "s3",
]
menu = "main"
author = "van"
+++

# AWS S3 Tips
This page gives some tips on how to manage the files and buckets in S3

## To list all the buckets (folders)
To get help for s3 command
```
$ aws s3 help
```

Try to run the following 
```
$ aws s3 ls
```

to list all the buckets using a specific profile
```
$ aws s3 --profile ${profile_name} ls
```

to list all the files in a specific bucket; say *test_bucket*
```
$ aws s3 ls s3://test_bucket
```

to list all the files in a specific bucket with a prefix *get*
```
$ aws s3 ls s3://test_bucket/get
```

to delete a file with prefix
```
$ aws s3 rm s3://test_bucket/${file_name}
```

to delete all files in a bucket 
```
$ aws s3 rm s3://${bucket_name}
```

to delete all files in a bucket using a specific profile
```
$ aws s3 --profile ${profile_name} rm s3://${bucket_name}
```

to delete a bucket
```
$ aws s3 rb s3://${bucket_name}
```

