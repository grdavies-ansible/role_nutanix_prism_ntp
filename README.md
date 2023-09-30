# Nutanix Role for Prism NTP server configuration

This Ansible role sets the NTP server configuration for Prism Element and Prism Central.

## Role Variables

| Variable                                   | Required | Default | Choices                                                                         | Comments                                                                                                                                           |
|--------------------------------------------|----------|---------|---------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| role_nutanix_prism_ntp_host                | yes      |         |                                                                                 | The IP address or FQDN for the Prism (Element or Central) to which you want to connect.                                                            |
| role_nutanix_prism_ntp_host_username       | yes      |         |                                                                                 | A valid username with appropriate rights to access the Nutanix API.                                                                                |
| role_nutanix_prism_ntp_host_password       | yes      |         |                                                                                 | A valid password for the supplied username.                                                                                                        |
| role_nutanix_prism_ntp_host_port           | no       | 9440    |                                                                                 | The Prism TCP port.                                                                                                                                |
| role_nutanix_prism_ntp_host_validate_certs | no       | false   | true / false                                                                    | Whether to check if Prism UI certificates are valid.                                                                                               |
| role_nutanix_prism_ntp_debug               | no       | false   | true / false                                                                    | Whether to check if Prism UI certificates are valid.                                                                                               |
| role_nutanix_prism_ntp_list                | yes      | []      |                                                                                 | Provide a list of NTP servers; ["0.pool.ntp.org", "1.pool.ntp.org", "2.pool.ntp.org", "3.pool.ntp.org"].                                                                                 |

## Dependencies

- grdavies.role_nutanix_prism_api

## Example Playbook

```YAML
- hosts: localhost
  gather_facts: false
  roles:
    - role: grdavies.role_nutanix_prism_ntp
  vars:
    role_nutanix_prism_ntp_host: 10.38.185.37
    role_nutanix_prism_ntp_host_username: admin
    role_nutanix_prism_ntp_host_password: nx2Tech165!
    prism_ntp_server_list:
      - 0.pool.ntp.org
      - 1.pool.ntp.org
      - 2.pool.ntp.org
      - 3.pool.ntp.org
```

## License

See LICENSE.md

## Author Information

Ross Davies
