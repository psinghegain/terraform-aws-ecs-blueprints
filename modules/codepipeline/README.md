# AWS CodePipeline

<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | >= 1.0.0 |
| <a name="requirement_aws"></a> [aws](#requirement\_aws) | >= 3.72.0 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_aws"></a> [aws](#provider\_aws) | >= 3.72.0 |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [aws_codepipeline.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/codepipeline) | resource |
| [aws_iam_policy.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_policy) | resource |
| [aws_iam_role.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_role) | resource |
| [aws_iam_role_policy_attachment.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_role_policy_attachment) | resource |
| [aws_iam_policy_document.assume_role_policy](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/iam_policy_document) | data source |
| [aws_iam_policy_document.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/iam_policy_document) | data source |
| [aws_partition.current](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/partition) | data source |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_app_deploy_configuration"></a> [app\_deploy\_configuration](#input\_app\_deploy\_configuration) | The configuration to use for the client deployment | `map(string)` | `{}` | no |
| <a name="input_branch"></a> [branch](#input\_branch) | Github branch used to trigger the CodePipeline | `string` | n/a | yes |
| <a name="input_code_build_projects"></a> [code\_build\_projects](#input\_code\_build\_projects) | The Code Build projects to which grant IAM access | `list(string)` | <pre>[<br>  "*"<br>]</pre> | no |
| <a name="input_code_deploy_resources"></a> [code\_deploy\_resources](#input\_code\_deploy\_resources) | The Code Deploy applications and deployment groups to which grant IAM access | `list(string)` | <pre>[<br>  "*"<br>]</pre> | no |
| <a name="input_codebuild_project_app"></a> [codebuild\_project\_app](#input\_codebuild\_project\_app) | Server's CodeBuild project name | `string` | n/a | yes |
| <a name="input_create_iam_role"></a> [create\_iam\_role](#input\_create\_iam\_role) | Set this variable to true if you want to create a role for AWS DevOps Tools | `bool` | `false` | no |
| <a name="input_deploy_provider"></a> [deploy\_provider](#input\_deploy\_provider) | The provider to use for deployment | `string` | `"ECS"` | no |
| <a name="input_github_token"></a> [github\_token](#input\_github\_token) | Personal access token from Github | `string` | n/a | yes |
| <a name="input_iam_role_name"></a> [iam\_role\_name](#input\_iam\_role\_name) | The name for the Role | `string` | n/a | yes |
| <a name="input_name"></a> [name](#input\_name) | The CodePipeline pipeline name | `string` | n/a | yes |
| <a name="input_repo_name"></a> [repo\_name](#input\_repo\_name) | Github repository's name | `string` | n/a | yes |
| <a name="input_repo_owner"></a> [repo\_owner](#input\_repo\_owner) | The username of the Github repository owner | `string` | n/a | yes |
| <a name="input_s3_bucket"></a> [s3\_bucket](#input\_s3\_bucket) | S3 bucket used for the artifact store | <pre>object({<br>    s3_bucket_id  = string<br>    s3_bucket_arn = string<br>  })</pre> | n/a | yes |
| <a name="input_service_role"></a> [service\_role](#input\_service\_role) | Amazon Resource Name (ARN) of the AWS Identity and Access Management (IAM) role that enables AWS CodeBuild to interact with dependent AWS services on behalf of the AWS account | `string` | n/a | yes |
| <a name="input_sns_topic"></a> [sns\_topic](#input\_sns\_topic) | The ARN of the SNS topic to use for pipline notifications | `string` | n/a | yes |
| <a name="input_tags"></a> [tags](#input\_tags) | tags | `map(string)` | `{}` | no |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_codepipeline_role_arn"></a> [codepipeline\_role\_arn](#output\_codepipeline\_role\_arn) | The ARN of the IAM role |
| <a name="output_codepipeline_role_name"></a> [codepipeline\_role\_name](#output\_codepipeline\_role\_name) | The name of the IAM role |
<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
