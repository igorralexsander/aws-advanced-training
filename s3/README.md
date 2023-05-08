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
* Maximum is 5 Terabytes via CLI

## Performance

You can get the first byte of file in 100-200 ms latency. 
You can also achieve a high number of requests: 3500 `PUT/COPY/POST/DELETE` and 5500 `GET/HEAD` requests per second per prefix.

## Event Notification

Only SQS or SNS Standard queue is allowed, SQS, SNS FIFO is not allowed.

## Byte Range Request

Using the Range HTTP header in a GET Object request, you can fetch a byte-range from an object, transferring only the specified portion. You can use concurrent connections to Amazon S3 to fetch different byte ranges from within the same object. This helps you achieve higher aggregate throughput versus a single whole-object request. Fetching smaller ranges of a large object also allows your application to improve retry times when requests are interrupted.

## Object Lock

Before you lock any objects, you have to enable a bucket to use S3 Object Lock. You enable Object Lock when you create a bucket. After you enable Object Lock on a bucket, you can lock objects in that bucket. When you create a bucket with Object Lock enabled, you can’t disable Object Lock or suspend versioning for that bucket.
The lock is done in version of file.

### Governance mode

Objects can be unlocked by users with special permissions.

### Compliance mode

Once an object is locked by compliance mode, this object remains locked until retention period end. Both regular users and root user can't unlock this object.

### Legal hold

Lock object without retention period, any user can atach legal hold in an object.

## Lifecycle transitions

Amazon S3 does not support any of the following lifecycle transitions.

You can't transition from the following:

* Any storage class to the S3 Standard storage class.
* Any storage class to the reduced redundancy storage class.
* The S3 intelligent-tiering storage class to the s3 standard-IA storage class.
* The S3 One-Zone-IA storage class to the S3 Intelligent-Tiering, S3 Standard-IA, or S3 Glacier Instant Retrieval storage classes.

* For larger objects, there is a cost-benefit for transitioning to STANDARD_IA or ONEZONE_IA. Amazon S3 does not transition objects that are smaller than 128 KB to the STANDARD_IA or ONEZONE_IA storage classes because it’s not cost-effective.

* Objects must be stored for at least 30 days in the current storage class before you can transition them to STANDARD_IA or ONEZONE_IA. For example, you cannot create a lifecycle rule to transition objects to the STANDARD_IA storage class one day after you create them. Amazon S3 doesn’t transition objects within the first 30 days because newer objects are often accessed more frequently or deleted sooner than is suitable for STANDARD_IA or ONEZONE_IA storage.

* If you are transitioning noncurrent objects (in versioned buckets), you can transition only objects that are at least 30 days noncurrent to STANDARD_IA or ONEZONE_IA storage.

## Encryption

* The entity tag (ETag) in the response is not MD5 hash of the object data.

If your bucket is versioning-enabled, each object version that you upload by using this feature can have its own encryotion key. You are responsible for tracking which encryption key was used for which object version.

## SSE-KMS

* If you specify the `x-amz-server-side-encryption:aws:kms` header but don't provide the `x-amz-server-side-encryption-aws-kms-key-id` header, Amazon S3 uses the AWS managed key (aws/s3) to protect the data.

|Header|Description|
|--|--|
|`x-amz-server-side-encryption`| `aws:kms`|
|`x-amz-server-side-encryption-aws-kms-key-id`|Key ARN|
|`x-amz-server-side-encryption-context`||
|`x-amz-server-side-encryption-context`||



## SSE-C (Server Side Encryption with customer provided keys)

* You cannot use the Amazon S3 console to upload an object and request SSE-C. You also cannot use the console to update (for example, change the storage class or add metadata) an existing object stored using SSE-C.

### Required headers

|Header|Description|
|--|--|
|`x-amz-server-side-encryption-customer-algorithm`|Use this header to specify the encryption algorithm. The header value must be AES256.|
|`x-amz-server-side-encryption-customer-key`|Use this header to provide the 256-bit, base64-encoded encryption key for Amazon S3 to use to encrypt or decrypt your data.|
|`x-amz-server-side-encryption-customer-key-MD5`|Use this header to provide the base64-encoded 128-bit MD5 digest of the encryption key according to RFC 1321. Amazon S3 uses this header for a message integrity check to ensure that the encryption key was transmitted without error.|