# AWS S3 Knowledge

* S3 Standard
* S3 Intelligent Tiering
* S3 Standard-IA
* S3 One Zone-IA
* S3 Glacier Instant Retrieval
* S3 Glacier Flexibe Retrieval

## AWS Inteligent Tiering

Move object between S3 Standard and S3 Standard IA.


## Minimum capacity charge per object

| Storage class                 | Apply |
| ----------------------------- | ----- |
| S3 Standard                   |     X |
| S3 Intelligent Tiering        |     X |
| S3 Stardard IA                | 128KB |
| S3 One Zone IA                | 128KB |
| S3 Glacier Instant Retrieval  | 128KB |
| S3 Glacier Flexible Retrieval |  40KB |
| S3 Glacier Deep Archive       |  40KB |

## Minimum storage duration charge

| Storage class                 |    Apply |
| ----------------------------- | -------- |
| S3 Standard                   |        X |
| S3 Intelligent Tiering        |        X |
| S3 Stardard IA                |  30 Days |
| S3 One Zone IA                |  30 Days |
| S3 Glacier Instant Retrieval  |  90 Days |
| S3 Glacier Flexible Retrieval |  90 Days |
| S3 Glacier Deep Archive       | 180 Days |

## Retrieval charge

| Storage class                 |   Apply |
| ----------------------------- |   ----- |
| S3 Standard                   |       X |
| S3 Intelligent Tiering        |       X |
| S3 Stardard IA                | Per GB  |
| S3 One Zone IA                | Per GB  |
| S3 Glacier Instant Retrieval  | Per GB  |
| S3 Glacier Flexible Retrieval | Per GB  |
| S3 Glacier Deep Archive       | Per GB  |

## First byte latency

| Storage class                 |             Apply |
| ----------------------------- |             ----- |
| S3 Standard                   | milliseconds      |
| S3 Intelligent Tiering        | milliseconds      |
| S3 Stardard IA                | milliseconds      |
| S3 One Zone IA                | milliseconds      |
| S3 Glacier Instant Retrieval  | milliseconds      |
| S3 Glacier Flexible Retrieval | minutes or hours  |
| S3 Glacier Deep Archive       | hours             |


## URLs

Bucket name id: `my-super-bucket` valid urls are:
* `https://my-super-bucket.s3.us-east-1.amazonaws.com`
* `https://s3.us-east-1.amazonaws.com/my-super-bucket`

## Static Web Site URLs

http://bucket-name.s3-website.Region.amazonaws.com

http://bucket-name.s3-website-Region.amazonaws.com

## Object size

* Minimum is 0 Bytes
* Maximum is 5 Terabytes

## Event Notification

Only SQS Standard queue is allowed, SQS FIFO is not allowed.

## Byte Range Request

Using the Range HTTP header in a GET Object request, you can fetch a byte-range from an object, transferring only the specified portion. You can use concurrent connections to Amazon S3 to fetch different byte ranges from within the same object. This helps you achieve higher aggregate throughput versus a single whole-object request. Fetching smaller ranges of a large object also allows your application to improve retry times when requests are interrupted.

## Object Lock

Before you lock any objects, you have to enable a bucket to use S3 Object Lock. You enable Object Lock when you create a bucket. After you enable Object Lock on a bucket, you can lock objects in that bucket. When you create a bucket with Object Lock enabled, you can’t disable Object Lock or suspend versioning for that bucket.

### Governance mode

Objects can be unlocked by users with special permissions.

### Compliance mode

Once an object is locked by compliance mode, this object remains locked until retention period end. Both regular users and root user can unlock this object.

### Legal hold

Lock object without retention period, any user can atach legal hold in an object.