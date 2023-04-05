# AWS Load Balancers

## Classic Load Balancer

* Sticky sessions, EC2 Level

## ALB (Application Load Balancer)

* Connection Termination
* Client IP on ec2 target is loadbalancer ip
* Real client IP is in custom header `X-Forwarded-For`
* Obrigatory security group
* sticky session, target  group level
* By default, cross-zone load balancing is enabled for Application Load Balancer

## NLB (Network Load Balancer)

* No connection termination
* Preserve ClientIP
* No Have a Security group
* If you register instances by `instance-id`
 Traffic is routed to instances using the primary private IP Address specified in the primary network interface for the instance.
* If you register instances by Private IP, you can inform both primary network inerface IP or case have a secondary network interface, you can inform the secondary network interface private IP.
* By default, cross-zone load balancing is disabled for Network Load Balancer

##