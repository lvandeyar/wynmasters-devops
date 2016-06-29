vpc
=========

This cloud formation file will build the following infrastructure components:

- VPC
- Public Subnets (in two AZ's)
- Private Subnets (in two AZ's)
- Database Subnets (in two AZ's)
- MGMT Subnets (in two AZ's)
- Public Security group
- Private Security group
- Database Security group
- MGMT Security group
- SFTP Security group
- Router
- Internet Gateway
- NAT Gateway (in two AZ's)
- Public Routing table
- Private Routing table (in two AZ's)
- Elastic IPs for both NAT Gateways
- Route53 Private Zone
- DHCP Options Set

Updating the Stack
------------

Any updates to the infrastructure should be done through the stack. The stack should be checked into GitHub to source control, then updated through the web portal or API.

vpc-params.json
------------

The params file should have the following data structure:

```sh
[{
  "ParameterKey": "SubnetAZ1",
  "ParameterValue": "value"
}, {
  "ParameterKey": "SubnetAZ2",
  "ParameterValue": "value"
}]

```

Creating the Stack
------------
```sh
aws cloudformation create-stack --stack-name wyncode-devops-vpc --template-body file://vpc.json --parameters file://vpc-params.json --profile PROFILENAME
```

Author Information
------------------

Laurence Vandeyar
