---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "aquasec_acknowledge Resource - doc"
subcategory: ""
description: |-
  
---

# aquasec_acknowledge (Resource)



## Example Usage

```terraform
resource "aquasec_acknowledge" "acknowledge" {
  comment = "comment"
  issues {
    docker_id        = ""
    image_name       = "image:latest"
    issue_name       = "CVE-2022-1271"
    issue_type       = "vulnerability"
    registry_name    = "registry"
    resource_cpe     = "cpe:/a:gnu:gzip:1.10"
    resource_name    = "gzip"
    resource_path    = "/usr/bin/gzip"
    resource_type    = "executable"
    resource_version = "1.10"
  }

  issues {
    docker_id        = "docker-id"
    image_name       = "image-name"
    issue_name       = "ALAS2-2021-1722"
    issue_type       = "vulnerability"
    registry_name    = "registry-name"
    resource_cpe     = "pkg:/amzn:2:nss-softokn:3.44.0-8.amzn2"
    resource_name    = "nss-softokn"
    resource_path    = ""
    resource_type    = "package"
    resource_version = "3.44.0-8.amzn2"
  }
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `comment` (String) A comment describing the reason for the acknowledgment
- `issues` (Block Set, Min: 1) A list of existing security acknowledges. (see [below for nested schema](#nestedblock--issues))

### Read-Only

- `id` (String) The ID of this resource.

<a id="nestedblock--issues"></a>
### Nested Schema for `issues`

Required:

- `issue_name` (String) The name of the security issue (the CVE or security advisory for vulnerabilities, name of malware or type of sensitive data)
- `issue_type` (String) The type of the security issue (either 'vulnerability', 'sensitive_data' or 'malware')
- `resource_type` (String) The type of the resource where the issue was detected (either 'package', 'file' or 'executable')

Optional:

- `docker_id` (String)
- `expiration_days` (Number) Number of days until expiration of the acknowledgement. The value must be integer from 1 to 999, inclusive.
- `fix_version` (String) The version of the package that having a fix for the issue.
- `image_name` (String) Only acknowledge the issue in the context of the specified image (also requires 'registry_name')
- `os` (String) When the resource_type is 'package', the operating system is required (e.g., 'ubuntu', 'alpine').
- `os_version` (String) When the resource_type is 'package', the operating system version is required.
- `registry_name` (String) Only acknowledge the issue in the context of the specified repository (also requires 'registry_name').
- `resource_cpe` (String) The CPE of the resource as listed in the issue by the Aqua API. This is required for resources of type 'executable'. For packages and files, the next parameters can be specified instead.
- `resource_format` (String) The format of the resource.
- `resource_hash` (String) When the resource_type is 'file', the hash of the file is required
- `resource_name` (String) When the resource_type is 'package', the name of the package is required.
- `resource_path` (String) The path of the resource. This is required for resources of type 'file' and 'executable'.
- `resource_version` (String) When the resource_type is 'package', the version of the package is required

Read-Only:

- `author` (String) The user who acknowledged the issue.
- `date` (String) The date and time of the acknowledgment.
- `expiration_configured_at` (String) The current dat and time when the expiration was set
- `expiration_configured_by` (String) The user who set the expiration of the issue.
- `permission` (String) The permissions of the user who acknowledged the issue.


