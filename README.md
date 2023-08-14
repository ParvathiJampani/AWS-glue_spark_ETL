# AWS-Glue-Pyspark-ETL-Job


This module performs statistical analysis on the noval corona virus dataset. The implementation is specifically
designed for AWS Glue environment. Can be used as a Glue Pyspark Job.
The dataset being used was last updated on May 02, 2020. 
The Module performs the following Functions:
* Reads data from csv files stored on AWS S3
* Perfroms Extract, Transform, Load (ETL) operations. 
* Lists max Cases for each country/region and provice/state
* Lists max Deaths for each country/region and provice/state
* List max Recoveries for each country/region and provice/state
* stores the aggregated output in parquet format
* Create an IAm role for crawler
*S3 bucket policy:
{
  "Version": "2012-10-17",
  "Id": "GlueSparkETLJobPolicy",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "Service": "glue.amazonaws.com"
      },
      "Action": [
        "s3:GetObject",
        "s3:PutObject",
        "s3:ListBucket"
      ],
      "Resource": [
        "arn:aws:s3:::your-source-bucket/*",
        "arn:aws:s3:::your-destination-bucket/*"
      ]
    }
  ]
}


