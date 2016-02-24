Ansible Role: Oracle SOA Suite
==============================

Role aimed to install and configure Oracle SOA Suite. Currently it supports
12c releases (12.1.3, 12.2.1)

Requirements
------------

- Java Development Kit installed, depending in SOA Suite version (e.g: Oracle JDK 8 on SOA 12.2.1)
- This role is only supported in Red Hat related OS (Centos, Oracle Linux).

Role Variables
--------------

Defaults:

- _oracle_soa_version_: 12c
- _oracle_soa_release_: 12.2.1 # 12.2.1 12.1.3
- _oracle_soa_quick_installation_: yes
- _oracle_soa_install_bpm_: yes

Depending in your release:

__12.1.3__

- _oracle_soa_installers_12_1_3_1of1_: files/fmw_12.1.3.0.0_soa_Disk1_1of2.zip

- _oracle_soa_qs_installers_12_1_3_1of1_: files/fmw_12.1.3.0.0_soaqs_Disk1_1of1.zip

- _oracle_bpm_qs_installers_12_1_3_1of1_: files/fmw_12.1.3.0.0_bpmqs_Disk1_1of1.zip

__12.2.1__

- _oracle_soa_installers_12_2_1_1of1_: files/fmw_12.2.1.0.0_soa_Disk1_1of2.zip

- _oracle_soa_qs_installers_12_2_1_1of2_: files/fmw_12.2.1.0.0_soaqs_Disk1_1of2.zip
- _oracle_soa_qs_installers_12_2_1_2of2_: files/fmw_12.2.1.0.0_soaqs_Disk1_2of2.zip

- _oracle_bpm_qs_installers_12_2_1_1of2_: files/fmw_12.2.1.0.0_bpmqs_Disk1_1of2.zip
- _oracle_bpm_qs_installers_12_2_1_2of2_: files/fmw_12.2.1.0.0_bpmqs_Disk1_2of2.zip

Variables:

- _oracle_soa_os_user_: oraclefmw
- _oracle_soa_os_group_: ofmwinstall
- _oracle_soa_os_user_home_: "/home/{{ oracle_soa_os_user }}"
- _oracle_soa_oracle_home_: "{{ oracle_soa_os_user_home }}/product/oracle_home"
- _oracle_soa_inventory_file_: "{{ oracle_soa_os_user_home }}/oraInst.loc"
- _oracle_soa_inventory_directory_: "{{ oracle_soa_os_user_home }}/ora_inventory"
- _oracle_soa_jdev_command_: jdev

- _oracle_soa_domains_home_: "{{ oracle_soa_os_user_home }}/config/domains"
- _oracle_soa_applications_home_: "{{ oracle_soa_os_user_home }}config/applications"

- _oracle_soa_already_installed_: false

Dependencies
------------

None.

Example Playbook
----------------

Refer to tests/test.yml

License
-------

MIT

Author Information
------------------

Jorge Quilcate (jorge.quilcate@sysco.no)
