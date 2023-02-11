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
