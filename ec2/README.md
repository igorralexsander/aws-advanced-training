# EC2

## Lifecycle Manager
Allow schedule automatic snapshots of volumes or instances.

## Placement Groups
Allow us to manage how instances will be distributed across availability zones
* Cluster (default)
* Spread
* Partition


## EC2 Metadata

All lauched EC2 instances make your metadata availble in http endpoints [Documentation](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/ec2-instance-metadata.html)

### Endpoint
```
http://169.254.169.254/latest
```