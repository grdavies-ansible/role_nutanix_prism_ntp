# Nutanix Role for Prism NTP server configuration

This Ansible role sets the NTP server configuration for Prism Element and Prism Central.


## Role Variables

| Variable                 | Required | Default | Choices                                                                         | Comments                                                                                                                                           |
|--------------------------|----------|---------|---------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| nutanix_host             | yes      |         |                                                                                 | The IP address or FQDN for the Prism (Element or Central) to which you want to connect.                                                            |
| nutanix_username         | yes      |         |                                                                                 | A valid username with appropriate rights to access the Nutanix API.                                                                                |
| nutanix_password         | yes      |         |                                                                                 | A valid password for the supplied username.                                                                                                        |
| nutanix_port             | no       | 9440    |                                                                                 | The Prism TCP port.                                                                                                                                |
| validate_certs           | no       | no      | yes / no                                                                        | Whether to check if Prism UI certificates are valid.                                                                                               |
| nutanix_ntp_server_list    | yes      | []      |                                                                                 | Provide a list of NTP servers; ["0.pool.ntp.org", "1.pool.ntp.org", "2.pool.ntp.org", "3.pool.ntp.org"].                                                                                 |

## Dependencies

NA

## Example Playbook

```
- hosts: localhost
  gather_facts: false
  roles:
    - role: grdavies.role_nutanix_prism_ntp
  vars:
    nutanix_host: 10.38.185.37
    nutanix_username: admin
    nutanix_password: nx2Tech165!
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
