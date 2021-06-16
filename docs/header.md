# terraform-aws-vpc-peering

Terraform Module for [AWS VPC Peering](https://docs.aws.amazon.com/vpc/latest/peering/what-is-vpc-peering.html)

## Usage

```hcl-terraform
module "vpc-peering" {
  source = "cornfeedhobo/vpc-peering/aws"

  providers = {
    "aws.requester" = "aws.ash"
    "aws.accepter"  = "aws.pdx"
  }

  // see Inputs for the rest of the configuration values
}
```

