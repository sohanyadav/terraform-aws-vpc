<!-- This file was automatically generated by the `geine`. Make all changes to `README.yaml` and run `make readme` to rebuild this file. -->

<p align="center"> <img src="https://user-images.githubusercontent.com/50652676/62349836-882fef80-b51e-11e9-99e3-7b974309c7e3.png" width="100" height="100"></p>


<h1 align="center">
    Terraform AWS VPC
</h1>

<p align="center" style="font-size: 1.2rem;">
    Terraform module to create VPC resource on AWS.
     </p>

<p align="center">

<a href="https://www.terraform.io">
  <img src="https://img.shields.io/badge/Terraform-v0.12-green" alt="Terraform">
</a>
<a href="LICENSE.md">
  <img src="https://img.shields.io/badge/License-MIT-blue.svg" alt="Licence">
</a>


</p>
<p align="center">

<a href='https://facebook.com/sharer/sharer.php?u=https://github.com/clouddrove/terraform-aws-vpc'>
  <img title="Share on Facebook" src="https://user-images.githubusercontent.com/50652676/62817743-4f64cb80-bb59-11e9-90c7-b057252ded50.png" />
</a>
<a href='https://www.linkedin.com/shareArticle?mini=true&title=Terraform+AWS+VPC&url=https://github.com/clouddrove/terraform-aws-vpc'>
  <img title="Share on LinkedIn" src="https://user-images.githubusercontent.com/50652676/62817742-4e339e80-bb59-11e9-87b9-a1f68cae1049.png" />
</a>
<a href='https://twitter.com/intent/tweet/?text=Terraform+AWS+VPC&url=https://github.com/clouddrove/terraform-aws-vpc'>
  <img title="Share on Twitter" src="https://user-images.githubusercontent.com/50652676/62817740-4c69db00-bb59-11e9-8a79-3580fbbf6d5c.png" />
</a>

</p>
<hr>


We eat, drink, sleep and most importantly love **DevOps**. We are working towards stratergies for standardizing architecture while ensuring security for the infrastructure. We are strong believer of the philosophy <b>Bigger problems are always solved by breaking them into smaller manageable problems</b>. Resonating with microservices architecture, it is considered best-practice to run database, cluster, storage in smaller <b>connected yet manageable pieces</b> within the infrastructure.

This module is basically combination of [Terraform open source](https://www.terraform.io/) and includes automatation tests and examples. It also helps to create and improve your infrastructure with minimalistic code instead of maintaining the whole infrastructure code yourself.

We have [*fifty plus terraform modules*][terraform_modules]. A few of them are comepleted and are available for open source usage while a few others are in progress.




## Prerequisites

This module has a few dependencies:

- [Terraform 0.12](https://learn.hashicorp.com/terraform/getting-started/install.html)
- [Go](https://golang.org/doc/install)
- [github.com/stretchr/testify/assert](https://github.com/stretchr/testify)
- [github.com/gruntwork-io/terratest/modules/terraform](https://github.com/gruntwork-io/terratest)






## Examples

**IMPORTANT:** Since the `master` branch used in `source` varies based on new modifications, we suggest that you use the release versions [here](https://github.com/clouddrove/terraform-aws-vpc/releases).


### Simple Example
Here is an example of how you can use this module in your inventory structure:
  ```hcl
  module "vpc" {
      source      = "git::https://github.com/clouddrove/terraform-aws-vpc.git"
      name        = "vpc"
      application = "clouddrove"
      environment = "test"
      label_order = ["environment", "name", "application"]
      cidr_block  = "10.0.0.0/16"
    }
  ```



## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| application | Application (e.g. `cd` or `clouddrove`). | string | `` | no |
| attributes | Additional attributes (e.g. `1`). | list | `<list>` | no |
| cidr_block | CIDR for the VPC. | string | `` | no |
| enable_classiclink | A boolean flag to enable/disable ClassicLink for the VPC. | bool | `false` | no |
| enable_classiclink_dns_support | A boolean flag to enable/disable ClassicLink DNS Support for the VPC. | bool | `false` | no |
| enable_dns_hostnames | A boolean flag to enable/disable DNS hostnames in the VPC. | bool | `true` | no |
| enable_dns_support | A boolean flag to enable/disable DNS support in the VPC. | bool | `true` | no |
| enable_flow_log | Enable vpc_flow_log logs. | bool | `false` | no |
| environment | Environment (e.g. `prod`, `dev`, `staging`). | string | `` | no |
| instance_tenancy | A tenancy option for instances launched into the VPC. | string | `default` | no |
| label_order | Label order, e.g. `name`,`application`. | list | `<list>` | no |
| name | Name  (e.g. `app` or `cluster`). | string | `` | no |
| s3_bucket_arn | S3 ARN for vpc logs. | string | `` | no |
| tags | Additional tags (e.g. map(`BusinessUnit`,`XYZ`). | map | `<map>` | no |
| traffic_type | Type of traffic to capture. Valid values: ACCEPT,REJECT, ALL. | string | `ALL` | no |
| vpc_enabled | Flag to control the vpc creation. | bool | `true` | no |

## Outputs

| Name | Description |
|------|-------------|
| igw_id | The ID of the Internet Gateway. |
| ipv6_cidr_block | The IPv6 CIDR block. |
| tags | A mapping of tags to assign to the resource. |
| vpc_cidr_block | The CIDR block of the VPC. |
| vpc_default_network_acl_id | The ID of the network ACL created by default on VPC creation. |
| vpc_default_route_table_id | The ID of the route table created by default on VPC creation. |
| vpc_default_security_group_id | The ID of the security group created by default on VPC creation. |
| vpc_id | The ID of the VPC. |
| vpc_ipv6_association_id | The association ID for the IPv6 CIDR block. |
| vpc_main_route_table_id | The ID of the main route table associated with this VPC. |



## Testing

In this module testing is performed with [terratest](https://github.com/gruntwork-io/terratest) and it creates a small piece of infrastructure, matches the output like ARN, ID and Tags name etc and destroy infrastructure in your AWS account. This testing is written in GO, so you need a [GO environment](https://golang.org/doc/install) in your system.

You need to run the following command in the testing folder:
```hcl
  go test -run Test
```



## Feedback
If you come accross a bug or have any feedback, please log it in our [issue tracker](https://github.com/clouddrove/terraform-aws-vpc/issues), or feel free to drop us an email at [hello@clouddrove.com](mailto:hello@clouddrove.com).

If you have found it worth your time, go ahead and give us a * on [our GitHub](https://github.com/clouddrove/terraform-aws-vpc)!

## About us

At [CloudDrove][website], we offer expert guidance, implementation support and services to help organisations accelerate their journey to the cloud. Our services include docker and container orchestration, cloud migration and adoption, infrastructure automation, application modernisation and remediation, and performance engineering.

<p align="center">We are <b> The Cloud Experts!</b></p>
<hr />
<p align="center">We ❤️  <a href="https://github.com/clouddrove">Open Source</a> and you can check out <a href="https://github.com/clouddrove">our other modules</a> to get help with your new Cloud ideas.</p>

  [website]: https://clouddrove.com
  [github]: https://github.com/clouddrove
  [linkedin]: https://cpco.io/linkedin
  [twitter]: https://twitter.com/clouddrove/
  [email]: https://clouddrove.com/contact-us.html
  [terraform_modules]: https://github.com/clouddrove?utf8=%E2%9C%93&q=terraform-&type=&language=