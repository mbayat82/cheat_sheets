### Architecture 
EIP: Elastic IP  
IGW: Internet Gateway  
RT: Route Table  
ENI: Elastic Network Interface  
NATGW: NAT Gateway  
VPCE: VPC End-Point  
[AWS Limits](https://docs.aws.amazon.com/vpc/latest/userguide/amazon-vpc-limits.html)
```
Account
└── Region-1
    ├── EIP-1
    ├── S3-1
    └── VPC-1
        ├── IGW
        ├── SG-1
        ├── RT-1
        ├── NACL-1
        ├── VPCE-1
        └── AZ-1
            ├── Subnet-1 <RT><NACL>
            │   ├── NATGW-1 <EIP>
            │   └── ENI-1 <EIP><SG-1>
            │       └── EC2
            └── Subnet-2 <RT><NACL>
                └── ENI-2 <SG-1>
                    └── EC2
```
