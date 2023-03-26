# AWS Disaster Recover

## RPO

RPO - Recovery Point Objective. Its is the acceptable time for data loss, example:
Company A accept until uo to 1 hour of data loss in case of a disaster happens.

## RTO

RTO - Recovery Time Objective. After disaster how many minutes, hours, days is acceptable to up the environment, in another region, datacenter, cloudprovider, etc.

## Strategies

### Backup & Restore

* Time to recover: Hours
* Lower priority use cases
* Provision all aws resources after the event
* Restore backups after event
* Cost $

### Pilot Light

* Time to recover: 10s of finutes (dezenas de minutos)
* Data live
* Services Idle
* Provision some aws resources and scale after event
* Cost: $$

### Warm standby

* Time to recover: Minutes
* Always running but smaller
* Business critical
* Scale AWS Resources after event
* Coast $$$

### Multi-site active/active

* Time to recover: Real Time
* Zero downtime
* Near zero data loss
* Mission critical services
* Coast $$$$
