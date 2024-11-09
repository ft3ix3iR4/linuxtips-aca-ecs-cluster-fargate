# linuxtips-aca-ecs-cluster
Repo para infra do cluster ECS em FARGATE
<!-- BEGIN_TF_DOCS -->
## Requirements

No requirements.

## Providers

| Name | Version |
|------|---------|
| <a name="provider_aws"></a> [aws](#provider\_aws) | 5.66.0 |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [aws_ecs_cluster.main](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ecs_cluster) | resource |
| [aws_ecs_cluster_capacity_providers.main](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ecs_cluster_capacity_providers) | resource |
| [aws_iam_instance_profile.main](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_instance_profile) | resource |
| [aws_iam_role.main](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_role) | resource |
| [aws_iam_role_policy_attachment.ec2_role](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_role_policy_attachment) | resource |
| [aws_iam_role_policy_attachment.ec2_ssm](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_role_policy_attachment) | resource |
| [aws_lb.internal](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/lb) | resource |
| [aws_lb.main](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/lb) | resource |
| [aws_lb_listener.internal](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/lb_listener) | resource |
| [aws_lb_listener.main](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/lb_listener) | resource |
| [aws_route53_record.wildcard](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/route53_record) | resource |
| [aws_route53_zone.private](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/route53_zone) | resource |
| [aws_security_group.lb](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group) | resource |
| [aws_security_group.lb_internal](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group) | resource |
| [aws_security_group.main](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group) | resource |
| [aws_security_group_rule.ingress_443](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group_rule) | resource |
| [aws_security_group_rule.ingress_80](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group_rule) | resource |
| [aws_security_group_rule.internal_ingress_443](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group_rule) | resource |
| [aws_security_group_rule.internal_ingress_80](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group_rule) | resource |
| [aws_security_group_rule.subnet_ranges](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group_rule) | resource |
| [aws_service_discovery_private_dns_namespace.main](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/service_discovery_private_dns_namespace) | resource |
| [aws_service_discovery_private_dns_namespace.sc](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/service_discovery_private_dns_namespace) | resource |
| [aws_ssm_parameter.cloudmap](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ssm_parameter) | resource |
| [aws_ssm_parameter.lb_arn](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ssm_parameter) | resource |
| [aws_ssm_parameter.lb_internal_arn](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ssm_parameter) | resource |
| [aws_ssm_parameter.lb_internal_listener](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ssm_parameter) | resource |
| [aws_ssm_parameter.lb_listener](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ssm_parameter) | resource |
| [aws_ssm_parameter.service_connect](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ssm_parameter) | resource |
| [aws_ssm_parameter.service_connect_name](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ssm_parameter) | resource |
| [aws_ssm_parameter.private_subnet_1a](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/ssm_parameter) | data source |
| [aws_ssm_parameter.private_subnet_1b](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/ssm_parameter) | data source |
| [aws_ssm_parameter.private_subnet_1c](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/ssm_parameter) | data source |
| [aws_ssm_parameter.public_subnet_1a](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/ssm_parameter) | data source |
| [aws_ssm_parameter.public_subnet_1b](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/ssm_parameter) | data source |
| [aws_ssm_parameter.public_subnet_1c](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/ssm_parameter) | data source |
| [aws_ssm_parameter.vpc](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/ssm_parameter) | data source |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_capacity_providers"></a> [capacity\_providers](#input\_capacity\_providers) | A lista dos capacity providers que serão permitidos no cluster fargate. | `list(any)` | <pre>[<br/>  "FARGATE",<br/>  "FARGATE_SPOT"<br/>]</pre> | no |
| <a name="input_cluster_on_demand_desired_size"></a> [cluster\_on\_demand\_desired\_size](#input\_cluster\_on\_demand\_desired\_size) | O número desejado de instâncias on-demand no cluster ECS. | `number` | n/a | yes |
| <a name="input_cluster_on_demand_max_size"></a> [cluster\_on\_demand\_max\_size](#input\_cluster\_on\_demand\_max\_size) | O tamanho máximo do cluster ECS para instâncias on-demand. | `number` | n/a | yes |
| <a name="input_cluster_on_demand_min_size"></a> [cluster\_on\_demand\_min\_size](#input\_cluster\_on\_demand\_min\_size) | O tamanho mínimo do cluster ECS para instâncias on-demand. | `number` | n/a | yes |
| <a name="input_cluster_spots_desired_size"></a> [cluster\_spots\_desired\_size](#input\_cluster\_spots\_desired\_size) | O número desejado de instâncias spot no cluster ECS. | `number` | n/a | yes |
| <a name="input_cluster_spots_max_size"></a> [cluster\_spots\_max\_size](#input\_cluster\_spots\_max\_size) | O tamanho máximo do cluster ECS para instâncias spot. | `number` | n/a | yes |
| <a name="input_cluster_spots_min_size"></a> [cluster\_spots\_min\_size](#input\_cluster\_spots\_min\_size) | O tamanho mínimo do cluster ECS para instâncias spot. | `number` | n/a | yes |
| <a name="input_load_balancer_internal"></a> [load\_balancer\_internal](#input\_load\_balancer\_internal) | Define se o Load Balancer deve ser interno (true) ou externo (false). | `bool` | n/a | yes |
| <a name="input_load_balancer_type"></a> [load\_balancer\_type](#input\_load\_balancer\_type) | O tipo de Load Balancer a ser criado (ex: 'application' ou 'network'). | `string` | n/a | yes |
| <a name="input_node_ami"></a> [node\_ami](#input\_node\_ami) | A AMI a ser usada pelos nodes do cluster ECS. | `string` | n/a | yes |
| <a name="input_node_instance_type"></a> [node\_instance\_type](#input\_node\_instance\_type) | O tipo de instância EC2 a ser usado pelos nodes do ECS. | `string` | n/a | yes |
| <a name="input_node_volume_size"></a> [node\_volume\_size](#input\_node\_volume\_size) | O tamanho do volume, em GiB, a ser usado pelos nodes do ECS. | `number` | n/a | yes |
| <a name="input_node_volume_type"></a> [node\_volume\_type](#input\_node\_volume\_type) | O tipo de volume EBS a ser usado pelos nodes do ECS (ex: 'gp2', 'io1'). | `string` | n/a | yes |
| <a name="input_project_name"></a> [project\_name](#input\_project\_name) | O nome do projeto, usado para nomear recursos no escopo deste Terraform. | `string` | n/a | yes |
| <a name="input_region"></a> [region](#input\_region) | A região da AWS onde os recursos serão criados. | `string` | n/a | yes |
| <a name="input_ssm_private_subnet_1"></a> [ssm\_private\_subnet\_1](#input\_ssm\_private\_subnet\_1) | O ID da primeira subnet privada na VPC para recursos SSM. | `string` | n/a | yes |
| <a name="input_ssm_private_subnet_2"></a> [ssm\_private\_subnet\_2](#input\_ssm\_private\_subnet\_2) | O ID da segunda subnet privada na VPC para recursos SSM. | `string` | n/a | yes |
| <a name="input_ssm_private_subnet_3"></a> [ssm\_private\_subnet\_3](#input\_ssm\_private\_subnet\_3) | O ID da terceira subnet privada na VPC para recursos SSM. | `string` | n/a | yes |
| <a name="input_ssm_public_subnet_1"></a> [ssm\_public\_subnet\_1](#input\_ssm\_public\_subnet\_1) | O ID da primeira subnet pública na VPC para recursos SSM. | `string` | n/a | yes |
| <a name="input_ssm_public_subnet_2"></a> [ssm\_public\_subnet\_2](#input\_ssm\_public\_subnet\_2) | O ID da segunda subnet pública na VPC para recursos SSM. | `string` | n/a | yes |
| <a name="input_ssm_public_subnet_3"></a> [ssm\_public\_subnet\_3](#input\_ssm\_public\_subnet\_3) | O ID da terceira subnet pública na VPC para recursos SSM. | `string` | n/a | yes |
| <a name="input_ssm_vpc_id"></a> [ssm\_vpc\_id](#input\_ssm\_vpc\_id) | O ID da VPC onde os recursos relacionados ao SSM serão criados. | `string` | n/a | yes |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_cloudmap_ssm"></a> [cloudmap\_ssm](#output\_cloudmap\_ssm) | ID do Namespace de Service Discovery do Cluster |
| <a name="output_internal_load_balancer_dns"></a> [internal\_load\_balancer\_dns](#output\_internal\_load\_balancer\_dns) | O nome DNS do Load Balancer Interno criado. Esse valor pode ser usado para acessar o Load Balancer dentro da rede ou pela internet, dependendo da configuração. |
| <a name="output_lb_ssm_arn"></a> [lb\_ssm\_arn](#output\_lb\_ssm\_arn) | O Amazon Resource Name (ARN) do parâmetro do AWS Systems Manager (SSM) que armazena o ARN do Load Balancer. Esse valor pode ser usado para referenciar o ARN do Load Balancer em políticas de IAM, regras de segurança, ou em qualquer outro lugar que requeira o ARN do Load Balancer. |
| <a name="output_lb_ssm_listener"></a> [lb\_ssm\_listener](#output\_lb\_ssm\_listener) | O ID do parâmetro do AWS Systems Manager (SSM) que armazena o Listener do Load Balancer. Esse valor pode ser utilizado para referenciar o Listener em automações, scripts, ou dentro de outras configurações da AWS que necessitem do ID do Listener. |
| <a name="output_load_balancer_dns"></a> [load\_balancer\_dns](#output\_load\_balancer\_dns) | O nome DNS do Load Balancer criado. Esse valor pode ser usado para acessar o Load Balancer dentro da rede ou pela internet, dependendo da configuração. |
| <a name="output_service_connect_name_ssm"></a> [service\_connect\_name\_ssm](#output\_service\_connect\_name\_ssm) | Nome do Service Connect do Cluster |
| <a name="output_service_connect_ssm"></a> [service\_connect\_ssm](#output\_service\_connect\_ssm) | ID do Namespace de Service Connect do Cluster |
<!-- END_TF_DOCS -->