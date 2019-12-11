# terraform-alicloud-resourcedirectory
AliCloud Resource Directory (rd) Terraform Module
=============================================

Terraform module which creates RD resources on Alibaba Cloud.

These types of resources are supported:

* [RD](https://www.terraform.io/docs/providers/alicloud/r/slb.html)

Root module calls these modules which can also be used separately to create independent resources:

* [rd](https://github.com/terraform-alicloud-modules/terraform-alicloud-resourcedirectory/tree/master/modules/rd) - creates resource directory


`NOTE`:
* If rd instance network is internal, the `internet_charge_type` only is "PayByTraffic".

Usage
-----
You can use this in your terraform template with the following steps.

1. Adding a module resource to your template, e.g. main.tf


         module "tf-slb" {
            source = "alibaba/slb/alicloud"

            vswitch_id = "${var.vswitch_id}"

            name = "tf-module-slb"
            vswitch_id = "vsw-3fin3c4"
            internal = true
            bandwidth = 5
            spec = "slb.s1.small"

            instances = ["i-fqefvdfbec9d", "i-fn39g3v93h89br"]

         }

2. Setting values for the following variables through environment variables:

    - ALICLOUD_ACCESS_KEY
    - ALICLOUD_SECRET_KEY


Authors
-------
Created and maintained by WenJiang Luo(wjluo@cmbchina.com)

Reference
---------
* [Terraform-Provider-Alicloud Github](https://github.com/terraform-providers/terraform-provider-alicloud)
* [Terraform-Provider-Alicloud Release](https://releases.hashicorp.com/terraform-provider-alicloud/)
* [Terraform-Provider-Alicloud Docs](https://www.terraform.io/docs/providers/alicloud/index.html)
