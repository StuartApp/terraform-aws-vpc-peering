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

## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | >= 0.15 |
| <a name="requirement_aws"></a> [aws](#requirement\_aws) | ~> 3.0 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_aws.accepter"></a> [aws.accepter](#provider\_aws.accepter) | ~> 3.0 |
| <a name="provider_aws.requester"></a> [aws.requester](#provider\_aws.requester) | ~> 3.0 |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [aws_route.accepter](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/route) | resource |
| [aws_route.requester](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/route) | resource |
| [aws_vpc_peering_connection.requester](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/vpc_peering_connection) | resource |
| [aws_vpc_peering_connection_accepter.accepter](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/vpc_peering_connection_accepter) | resource |
| [aws_vpc_peering_connection_options.accepter](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/vpc_peering_connection_options) | resource |
| [aws_vpc_peering_connection_options.requester](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/vpc_peering_connection_options) | resource |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_accepter-account_id"></a> [accepter-account\_id](#input\_accepter-account\_id) | The AWS Account ID of the 'requester' VPC | `string` | n/a | yes |
| <a name="input_accepter-allow_remote_vpc_dns_resolution"></a> [accepter-allow\_remote\_vpc\_dns\_resolution](#input\_accepter-allow\_remote\_vpc\_dns\_resolution) | Toggle the allowance of DNS resolution through the 'requester' | `bool` | `false` | no |
| <a name="input_accepter-route_table_ids"></a> [accepter-route\_table\_ids](#input\_accepter-route\_table\_ids) | The VPC Route Table IDs of the 'accepter' VPC | `list(string)` | n/a | yes |
| <a name="input_accepter-vpc_cidr_blocks"></a> [accepter-vpc\_cidr\_blocks](#input\_accepter-vpc\_cidr\_blocks) | The VPC CIDR block of the 'accepter' VPC | `list(string)` | n/a | yes |
| <a name="input_accepter-vpc_id"></a> [accepter-vpc\_id](#input\_accepter-vpc\_id) | The VPC ID of the 'accepter' VPC | `string` | n/a | yes |
| <a name="input_enabled"></a> [enabled](#input\_enabled) | Toggle the creation and destruction of all resources in this module | `bool` | `true` | no |
| <a name="input_requester-allow_remote_vpc_dns_resolution"></a> [requester-allow\_remote\_vpc\_dns\_resolution](#input\_requester-allow\_remote\_vpc\_dns\_resolution) | Toggle the allowance of DNS resolution through the 'accepter' | `bool` | `false` | no |
| <a name="input_requester-route_table_ids"></a> [requester-route\_table\_ids](#input\_requester-route\_table\_ids) | The VPC Route Table IDs of the 'requester' VPC | `list(string)` | n/a | yes |
| <a name="input_requester-vpc_cidr_blocks"></a> [requester-vpc\_cidr\_blocks](#input\_requester-vpc\_cidr\_blocks) | The VPC CIDR block of the 'requester' VPC | `list(string)` | n/a | yes |
| <a name="input_requester-vpc_id"></a> [requester-vpc\_id](#input\_requester-vpc\_id) | The VPC ID of the 'requester' VPC | `string` | n/a | yes |
| <a name="input_tags"></a> [tags](#input\_tags) | Tags to attach to the peering resources | `map(string)` | `{}` | no |

## Outputs

No outputs.

## License

[MIT](LICENSE)

## Is it any good?

[Yes](http://news.ycombinator.com/item?id=3067434)