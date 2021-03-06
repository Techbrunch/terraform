---
layout: "aws"
page_title: "AWS: aws_efs_file_system"
sidebar_current: "docs-aws-resource-efs-file-system"
description: |-
  Provides an Elastic File System (EFS) resource.
---

# aws\_efs\_file\_system

Provides an Elastic File System (EFS) resource.

## Example Usage

```hcl
resource "aws_efs_file_system" "foo" {
  creation_token = "my-product"

  tags {
    Name = "MyProduct"
  }
}
```

## Argument Reference

~> **NOTE:** The `reference_name` attribute has been deprecated and might
be removed in future releases, please use `creation_token` instead.

The following arguments are supported:

* `creation_token` - (Optional) A unique name (a maximum of 64 characters are allowed)
used as reference when creating the Elastic File System to ensure idempotent file
system creation. By default generated by Terraform. See [Elastic File System]
(http://docs.aws.amazon.com/efs/latest/ug/) user guide for more information.
* `reference_name` - **DEPRECATED** (Optional) A reference name used when creating the
`Creation Token` which Amazon EFS uses to ensure idempotent file system creation. By
default generated by Terraform.
* `performance_mode` - (Optional) The file system performance mode. Can be either
`"generalPurpose"` or `"maxIO"` (Default: `"generalPurpose"`).
* `tags` - (Optional) A mapping of tags to assign to the file system.

## Attributes Reference

The following attributes are exported:

* `id` - The ID that identifies the file system (e.g. fs-ccfc0d65).

## Import

The EFS file systems can be imported using the `id`, e.g.

```
$ terraform import aws_efs_file_system.foo fs-6fa144c6
```
