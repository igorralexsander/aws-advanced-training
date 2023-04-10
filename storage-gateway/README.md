# AWS Storage Gateway

* Tape Gateway
* S3 File Gateway
* FSx File Gateway
* Volume Gateway

## File Gateway (S3 File Gateway and FSx FileGateway)

It's not possible upload direct to S3 Glacier Storage Classes, to do this you have to create lifecycle transiton rule in s3 standard to transition objects to glacier.

## Tape Gateway

It's possible upload direct to all of S3 Glacier storage classes.
