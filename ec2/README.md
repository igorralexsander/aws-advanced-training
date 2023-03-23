# EC2

## Pricing Model

### Saving Plans

Os Savings Plans são um modelo de preço flexível que oferece preços baixos no uso do Amazon EC2, AWS Lambda e AWS Fargate em troca de um compromisso com uma quantidade consistente de uso (medido em USD/hora) por um período de um ou três anos. Ao se inscrever em um Savings Plan, você será cobrado pelo preço com desconto dos Savings Plans pelo uso até seu compromisso. A AWS oferece dois tipos de Savings Plans:

#### Compute Savings Plans

Os Compute Savings Plans fornecem a maior flexibilidade e ajudam a reduzir seus custos em até 66%. Esses planos se aplicam automaticamente ao uso da instância do EC2, independentemente de família de instâncias, tamanho, AZ, região, sistema operacional ou locação da instância, e também se aplicam ao uso do Fargate ou Lambda. Por exemplo, com os Compute Savings Plans, você pode mudar das instâncias C4 para M5, deslocar uma workload da região Europa (Irlanda) para a região Europa (Londres) ou mover uma workload do EC2 para o Fargate ou Lambda a qualquer momento e continuar pagando automaticamente o preço dos Savings Plans.

#### EC2 Instance Savings Plans

Os EC2 Instance Savings Plans fornecem os preços mais baixos, oferecendo economia de até 72% em troca do comprometimento com o uso de famílias de instâncias individuais em uma região (por exemplo, usar M5 no Norte da Virginia). Isso reduz automaticamente seu custo na família de instâncias selecionadas nessa região, qualquer que seja a AZ, o tamanho, o sistema operacional ou a locação. Os EC2 Instance Savings Plans oferecem a flexibilidade de alterar seu uso entre instâncias de uma família nessa região. Por exemplo, você pode passar de c5.xlarge executando Windows para c5.2xlarge executando Linux e se beneficiar automaticamente dos preços dos Savings Plan.

### Reserved Instances

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

``` http://169.254.169.254/latest/meta-data ```


## User data
Add commands to execute on first initialization of the instance.
User Data for an instance can be modified if it is in stopped state and the root volume is an EBS Volume.

By default, scripts entered as user data are executed with root user privileges - Scripts entered as user data are executed as the root user, hence do not need the sudo command in the script. Any files you create will be owned by root; if you need non-root users to have file access, you should modify the permissions accordingly in the script.

### Spot Intances

Spot blocks can only be used for a span of up to 6 hours.

Always you view `across multiple servers` think about `fleet spot intances, fleet on demand instances` because fleet is similat to set of instances.