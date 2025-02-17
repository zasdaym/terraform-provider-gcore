---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "gcore_lblistener Data Source - terraform-provider-gcore"
subcategory: ""
description: |-
  
---

# gcore_lblistener (Data Source)



## Example Usage

```terraform
provider gcore {
  permanent_api_token = "251$d3361.............1b35f26d8"
}

data "gcore_project" "project" {
  name = "Default"
}

data "gcore_region" "region" {
  name = "Luxembourg-2"
}

data "gcore_lblistener" "listener" {
  region_id  = data.gcore_region.region.id
  project_id = data.gcore_project.project.id

  name            = "test-listener"
  // loadbalancer_id = gcore.loadbalancer_v2.lb.id
}

output "view" {
  value = data.gcore_lblistener.listener
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `name` (String) Name of the load balancer listener.

### Optional

- `connection_limit` (Number) Number of simultaneous connections for this listener, between 1 and 1,000,000.
- `loadbalancer_id` (String) ID of the load balancer to which listener was attached.
- `project_id` (Number) ID of the project in which load balancer listener was created.
- `project_name` (String) Name of the project in which load balancer listener was created.
- `region_id` (Number) ID of the region in which load balancer listener was created.
- `region_name` (String) Name of the region in which load balancer listener was created.
- `timeout_client_data` (Number) Frontend client inactivity timeout in milliseconds.
- `timeout_member_connect` (Number) Backend member connection timeout in milliseconds.
- `timeout_member_data` (Number) Backend member inactivity timeout in milliseconds.

### Read-Only

- `id` (String) The ID of this resource.
- `operating_status` (String) Operating status of this listener.
- `pool_count` (Number) Number of pools in this listener.
- `protocol` (String) Available values are 'HTTP', 'HTTPS', 'TCP', 'UDP', 'TERMINATED_HTTPS', 'PROMETHEUS'
- `protocol_port` (Number) Port number to listen, between 1 and 65535.
- `provisioning_status` (String) Provisioning status of this listener.
