# terraform-provider-gobetween

Terraform Provider for the [gobetween](gobetween.io) load balancer 

## Status

Alpha - expect breaking changes

## Example Usage

```hcl
provider "gobetween" {
    host = "1.2.3.4"
    port = 8888
}

resource "gobetween_server" "example" {
    name = "example"
    balance = "weight"
    bind = "0.0.0.0:5858"
    discovery {
        static_list = ["1.2.3.4:80", "2.3.4.5:80"]
    }
}
```