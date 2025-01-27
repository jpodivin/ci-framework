# pci_passthrough
Role creates files necessary for enablement of PCI-passthrough.

## Parameters
* `pci_vendor_id`: Vendor ID of PCI device
* `pci_product_id`: Product ID of PCI device
* `pci_device_name`: Alias for device inside VM
* `pci_device_type`: Nova device type, can be one of 'type-PF', 'type-VF' or 'type-PCI'. Set to 'type-PCI' by default
* `pci_numa_policy`: Numa policy, one of 'requiered', 'legacy', 'preferred' or 'socket'. Set to 'legacy' by default.
* `enable_iommu`: Set to true to enable IOMMU on Intel CPUs. True by default.
* `pci_passthrough_flavor_name`: Name of compute flavor modified to support passthrough. Set to 'pci-passthrough-flavor' by default.

## Examples

```YAML
- name: Play
  hosts: localhost
  roles:
    - role: "pci_passthrough"
      vars:
        pci_vendor_id: "aaaa"
        pci_product_id: "bbbb"
        pci_device_name: "cccc"
```
