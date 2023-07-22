
# AWS Lambda


## Lambda in an VPC

By default a lambda deployed in a VPC does not have access to the internet, even if it was deployed in a public subnet.
If you want that your lambda function have access to the internet it's required a NAT Gateway in your subnet.

## Lambda and CodeDeploy

* Linear: Grow traffic N minutes until 100%
    * Linear10PercentEvery3Minutes
    * Linear10PercentEvery10Minutes
* Canary: Try X percent then 100%
    * Canary10Percente5Minutes
    * Canary10Percent30Minutes
* AllAtOnce: Immediate

## Environment Variables

* Up to 4KB