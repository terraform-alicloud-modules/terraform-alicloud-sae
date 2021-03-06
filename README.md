# terraform-alicloud-sae
Terraform Module for creating SAE resources on Alibaba Cloud.

English | [简体中文](https://github.com/terraform-alicloud-modules/terraform-alicloud-sae/blob/master/README-CN.md)

Terraform module which add new sae application on Alibaba Cloud and batch configuration for it.

These types of resources are supported:

* [alicloud_sae_namespace](https://registry.terraform.io/providers/aliyun/alicloud/latest/docs/resources/sae_namespace)
* [alicloud_sae_config_map](https://registry.terraform.io/providers/aliyun/alicloud/latest/docs/resources/sae_config_map)
* [alicloud_sae_application](https://registry.terraform.io/providers/aliyun/alicloud/latest/docs/resources/sae_application)

## Usage

Create a namespace and configure the following items under the namespace: Configuration List, Application.
```hcl
module "example" {
  source                 = "terraform-alicloud-modules/sae/alicloud"
  namespace_name         = "tftestacc"
  region                 = "cn-hangzhou"
  name                   = "tftestacc"
  config_map_description = "description"
  config_map_data        = "map_data"
  app_name               = "name"
  package_type           = "Image"
  vswitch_id             = "your_vswitch_id"
  vpc_id                 = "your_vpc_id"
  image_url              = "your_image_url"
  replicas               = 2
  cpu                    = 500
  memory                 = 2048
}
```

## Examples

* [complete example](https://github.com/terraform-alicloud-modules/terraform-alicloud-sae/tree/master/examples/complete)

## Terraform versions

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | >= 0.12.0 |
| <a name="requirement_alicloud"></a> [alicloud](#requirement\_alicloud) | >= 1.67.0 |

Authors
-------
Created and maintained by Alibaba Cloud Terraform Team(terraform@alibabacloud.com)

License
----
Apache 2 Licensed. See LICENSE for full details.

Reference
---------
* [Terraform-Provider-Alicloud Github](https://github.com/terraform-providers/terraform-provider-alicloud)
* [Terraform-Provider-Alicloud Release](https://releases.hashicorp.com/terraform-provider-alicloud/)
* [Terraform-Provider-Alicloud Docs](https://www.terraform.io/docs/providers/alicloud/index.html)
