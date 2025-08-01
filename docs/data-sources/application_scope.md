---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "aquasec_application_scope Data Source - terraform-provider-aquasec"
subcategory: ""
description: |-
  
---

# aquasec_application_scope (Data Source)



## Example Usage

```terraform
data "aquasec_application_scope" "default" {
  name = "Global"
}

output "scopes" {
  value = data.aquasec_application_scope.default
}

output "codebuild_config" {
  value = [
    for category in data.aquasec_application_scope.default.categories : [
      for artifact in category.artifacts : artifact.codebuild if artifact.codebuild != null
    ] if category.artifacts != null
  ][0][0]
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `name` (String) Name of an application scope.

### Optional

- `categories` (Block Set) Artifacts (of applications) / Workloads (containers) / Infrastructure (elements). (see [below for nested schema](#nestedblock--categories))

### Read-Only

- `author` (String) Username of the account that created the service.
- `description` (String) Description of the application scope.
- `id` (String) The ID of this resource.
- `owner_email` (String) Name of an application scope.

<a id="nestedblock--categories"></a>
### Nested Schema for `categories`

Optional:

- `artifacts` (Block Set) (see [below for nested schema](#nestedblock--categories--artifacts))
- `entity_scope` (Block Set) (see [below for nested schema](#nestedblock--categories--entity_scope))
- `infrastructure` (Block Set) (see [below for nested schema](#nestedblock--categories--infrastructure))
- `workloads` (Block Set) (see [below for nested schema](#nestedblock--categories--workloads))

<a id="nestedblock--categories--artifacts"></a>
### Nested Schema for `categories.artifacts`

Optional:

- `cf` (Block Set) (see [below for nested schema](#nestedblock--categories--artifacts--cf))
- `codebuild` (Block Set) (see [below for nested schema](#nestedblock--categories--artifacts--codebuild))
- `function` (Block Set) (see [below for nested schema](#nestedblock--categories--artifacts--function))
- `image` (Block Set) (see [below for nested schema](#nestedblock--categories--artifacts--image))

<a id="nestedblock--categories--artifacts--cf"></a>
### Nested Schema for `categories.artifacts.cf`

Optional:

- `expression` (String)
- `variables` (Block List) (see [below for nested schema](#nestedblock--categories--artifacts--cf--variables))

<a id="nestedblock--categories--artifacts--cf--variables"></a>
### Nested Schema for `categories.artifacts.cf.variables`

Optional:

- `attribute` (String)
- `name` (String)
- `value` (String)



<a id="nestedblock--categories--artifacts--codebuild"></a>
### Nested Schema for `categories.artifacts.codebuild`

Optional:

- `expression` (String)
- `variables` (Block List) (see [below for nested schema](#nestedblock--categories--artifacts--codebuild--variables))

<a id="nestedblock--categories--artifacts--codebuild--variables"></a>
### Nested Schema for `categories.artifacts.codebuild.variables`

Optional:

- `attribute` (String)
- `name` (String)
- `value` (String)



<a id="nestedblock--categories--artifacts--function"></a>
### Nested Schema for `categories.artifacts.function`

Optional:

- `expression` (String)
- `variables` (Block List) (see [below for nested schema](#nestedblock--categories--artifacts--function--variables))

<a id="nestedblock--categories--artifacts--function--variables"></a>
### Nested Schema for `categories.artifacts.function.variables`

Optional:

- `attribute` (String)
- `name` (String)
- `value` (String)



<a id="nestedblock--categories--artifacts--image"></a>
### Nested Schema for `categories.artifacts.image`

Optional:

- `expression` (String)
- `variables` (Block List) (see [below for nested schema](#nestedblock--categories--artifacts--image--variables))

<a id="nestedblock--categories--artifacts--image--variables"></a>
### Nested Schema for `categories.artifacts.image.variables`

Optional:

- `attribute` (String)
- `name` (String)
- `value` (String)




<a id="nestedblock--categories--entity_scope"></a>
### Nested Schema for `categories.entity_scope`

Optional:

- `expression` (String)
- `variables` (Block List) (see [below for nested schema](#nestedblock--categories--entity_scope--variables))

<a id="nestedblock--categories--entity_scope--variables"></a>
### Nested Schema for `categories.entity_scope.variables`

Optional:

- `attribute` (String)
- `name` (String)
- `value` (String)



<a id="nestedblock--categories--infrastructure"></a>
### Nested Schema for `categories.infrastructure`

Optional:

- `kubernetes` (Block Set) (see [below for nested schema](#nestedblock--categories--infrastructure--kubernetes))
- `os` (Block Set) (see [below for nested schema](#nestedblock--categories--infrastructure--os))

<a id="nestedblock--categories--infrastructure--kubernetes"></a>
### Nested Schema for `categories.infrastructure.kubernetes`

Optional:

- `expression` (String)
- `variables` (Block List) (see [below for nested schema](#nestedblock--categories--infrastructure--kubernetes--variables))

<a id="nestedblock--categories--infrastructure--kubernetes--variables"></a>
### Nested Schema for `categories.infrastructure.kubernetes.variables`

Optional:

- `attribute` (String)
- `name` (String)
- `value` (String)



<a id="nestedblock--categories--infrastructure--os"></a>
### Nested Schema for `categories.infrastructure.os`

Optional:

- `expression` (String)
- `variables` (Block List) (see [below for nested schema](#nestedblock--categories--infrastructure--os--variables))

<a id="nestedblock--categories--infrastructure--os--variables"></a>
### Nested Schema for `categories.infrastructure.os.variables`

Optional:

- `attribute` (String)
- `name` (String)
- `value` (String)




<a id="nestedblock--categories--workloads"></a>
### Nested Schema for `categories.workloads`

Optional:

- `cf` (Block Set) (see [below for nested schema](#nestedblock--categories--workloads--cf))
- `kubernetes` (Block Set) (see [below for nested schema](#nestedblock--categories--workloads--kubernetes))
- `os` (Block Set) (see [below for nested schema](#nestedblock--categories--workloads--os))

<a id="nestedblock--categories--workloads--cf"></a>
### Nested Schema for `categories.workloads.cf`

Optional:

- `expression` (String)
- `variables` (Block List) (see [below for nested schema](#nestedblock--categories--workloads--cf--variables))

<a id="nestedblock--categories--workloads--cf--variables"></a>
### Nested Schema for `categories.workloads.cf.variables`

Optional:

- `attribute` (String)
- `name` (String)
- `value` (String)



<a id="nestedblock--categories--workloads--kubernetes"></a>
### Nested Schema for `categories.workloads.kubernetes`

Optional:

- `expression` (String)
- `variables` (Block List) (see [below for nested schema](#nestedblock--categories--workloads--kubernetes--variables))

<a id="nestedblock--categories--workloads--kubernetes--variables"></a>
### Nested Schema for `categories.workloads.kubernetes.variables`

Optional:

- `attribute` (String)
- `name` (String)
- `value` (String)



<a id="nestedblock--categories--workloads--os"></a>
### Nested Schema for `categories.workloads.os`

Optional:

- `expression` (String)
- `variables` (Block List) (see [below for nested schema](#nestedblock--categories--workloads--os--variables))

<a id="nestedblock--categories--workloads--os--variables"></a>
### Nested Schema for `categories.workloads.os.variables`

Optional:

- `attribute` (String)
- `name` (String)
- `value` (String)


