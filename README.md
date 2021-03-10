# AWS Cross account access Terraform module

[![Labyrinth Labs logo](ll-logo.png)](https://www.lablabs.io)

We help companies build, run, deploy and scale software and infrastructure by embracing the right technologies and principles. Check out our website at https://lablabs.io/

---

![Terraform validation](https://github.com/lablabs/terraform-aws-cross-account-access/workflows/Terraform%20validation/badge.svg?branch=master)
[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-success?logo=pre-commit&logoColor=white)](https://github.com/pre-commit/pre-commit)

## Description

A terraform module to create a cross account access in Amazon AWS.

<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Requirements

| Name | Version |
|------|---------|
| terraform | >= 0.13 |
| aws | >= 2.0 |

## Modules

| Name | Source | Version |
|------|--------|---------|
| group_label | cloudposse/label/null | 0.24.1 |
| role_label | cloudposse/label/null | 0.24.1 |

## Resources

| Name |
|------|
| [aws_iam_group](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_group) |
| [aws_iam_group_policy_attachment](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_group_policy_attachment) |
| [aws_iam_policy](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_policy) |
| [aws_iam_policy_document](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/iam_policy_document) |
| [aws_iam_role](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_role) |
| [aws_iam_role_policy_attachment](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_role_policy_attachment) |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| assumable\_role\_permissions\_boundary\_arn | Permissions boundary ARN to use for IAM role | `string` | n/a | yes |
| assumable\_additional\_role\_policy\_arns | List of ARNs of IAM policies to attach to IAM role | `list(string)` | `[]` | no |
| assumable\_admin\_role\_policy\_arn | Policy ARN to use for admin role | `string` | `"arn:aws:iam::aws:policy/AdministratorAccess"` | no |
| assumable\_role\_attach\_admin\_policy | Whether to attach an admin policy to a role | `bool` | `false` | no |
| assumable\_role\_create | Whether to create a role in the caller account | `bool` | `true` | no |
| assumable\_role\_mfa | Whether role requires MFA | `bool` | `true` | no |
| assumable\_role\_name | IAM role name. Defaults to auto generated role name | `string` | `""` | no |
| assumable\_role\_name\_generated | Whether to create a role with assumable\_role\_name or autogenerated | `bool` | `false` | no |
| assumable\_role\_path | IAM role path | `string` | `"/"` | no |
| assumable\_role\_services | AWS Services that can assume these roles | `list(string)` | `[]` | no |
| assumable\_role\_trusted\_arns | ARNs of AWS entities who can assume these roles | `list(string)` | `[]` | no |
| assumable\_tags | A map of tags to add to IAM role resources | `map(string)` | `{}` | no |
| environment | Environment, e.g. 'prod', 'staging', 'dev', 'pre-prod', 'UAT' | `string` | `""` | no |
| group\_account\_role | Map of group and role to be assumend in another account. | `map(any)` | `{}` | no |
| group\_name\_prefix | Prefix of IAM group name | `string` | `""` | no |
| group\_name\_suffix | Suffix of IAM group name | `string` | `""` | no |
| namespace | Namespace, which could be your organization name or abbreviation, e.g. 'eg' or 'cp' | `string` | `""` | no |
| tags | Additional tags (e.g. `map('BusinessUnit','XYZ')` | `map(string)` | `{}` | no |

## Outputs

| Name | Description |
|------|-------------|
| assumable\_role\_additional\_policy | n/a |
| assumable\_role\_admin\_policy | n/a |
| assumable\_role\_arn | n/a |
| assumable\_role\_id | n/a |
| assumable\_role\_name | n/a |
| group\_arns | n/a |
| group\_ids | n/a |
| group\_names | n/a |
| group\_policy\_arns | n/a |
<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->

## Contributing and reporting issues

Feel free to create an issue in this repository if you have questions, suggestions or feature requests.

### Validation, linters and pull-requests

We want to provide high quality code and modules. For this reason we are using
several [pre-commit hooks](.pre-commit-config.yaml) and
[GitHub Actions workflow](.github/workflows/main.yml). A pull-request to the
master branch will trigger these validations and lints automatically. Please
check your code before you will create pull-requests. See
[pre-commit documentation](https://pre-commit.com/) and
[GitHub Actions documentation](https://docs.github.com/en/actions) for further
details.


## License

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

See [LICENSE](LICENSE) for full details.

    Licensed to the Apache Software Foundation (ASF) under one
    or more contributor license agreements.  See the NOTICE file
    distributed with this work for additional information
    regarding copyright ownership.  The ASF licenses this file
    to you under the Apache License, Version 2.0 (the
    "License"); you may not use this file except in compliance
    with the License.  You may obtain a copy of the License at

      https://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing,
    software distributed under the License is distributed on an
    "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
    KIND, either express or implied.  See the License for the
    specific language governing permissions and limitations
    under the License.
