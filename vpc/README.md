# AWS VPC



## Subnets

A subnet is implicitly associated with the main route table if it is not explicitly associated with a particular route table. So, a subnet is always associated with some route table.

A subnet can only be associated with one route table at a time.

## VPC internal domains Route53

On create VPC activate flags `enableDnsSupport` and `enableDnsHostnames`.