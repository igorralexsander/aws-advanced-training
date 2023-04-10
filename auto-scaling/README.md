# AWS Auto Scaling

## Termination policy

Per the default termination policy, the first priority is given to any allocation strategy for On-Demand vs Spot instances. As no such information has been provided for the given use-case, so this criterion can be ignored. The next priority is to consider any instance with the oldest launch template unless there is an instance that uses a launch configuration. So this rules out Instance A. Next, you need to consider any instance which has the oldest launch configuration. This implies Instance B will be selected for termination and Instance C will also be ruled out as it has the newest launch configuration. Instance D, which is closest to the next billing hour, is not selected as this criterion is last in the order of priority.

Instances that are marked for termination or that have failed health checks are terminated first.
Instances that have the oldest launch configuration are terminated next.
If multiple instances share the oldest launch configuration, Amazon EC2 Auto Scaling terminates the instances with the oldest launch template.
If multiple instances share the oldest launch configuration and launch template, Amazon EC2 Auto Scaling selects the instances with the oldest launch date.

## Launch Template

Used on autoscaling and direct launches in ec2 console.


## Launch Configuration

Used only autoscaling.

## Rebalancing activity

When rebalancing, Amazon EC2 Auto Scaling launches new instances before terminating the old ones, so that rebalancing does not compromise the performance or availability of your application. Therefore, this option is correct.

## Scaling activity

However, the `scaling activity` of Auto Scaling works in a different sequence compared to the rebalancing activity. Auto Scaling creates a new scaling activity for terminating the unhealthy instance and then terminates it. Later, another scaling activity launches a new instance to replace the terminated instance.