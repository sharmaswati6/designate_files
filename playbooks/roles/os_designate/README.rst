OpenStack Designate
###################
:tags: openstack, cloud, ansible, designate 
:category: \*nix

Role to install Designate and its services 

This role will install the following:
    * designate-api
    * designate-central
    * designate-pool_manager
    * designate-mdns
    * designate-sink 

.. code-block:: yaml

    - name: Install designate services
      hosts: designate_all
      user: root
      roles:
        - { role: "os_designate", tags: [ "os-designate" ] }
      vars:
        external_lb_vip_address: 172.16.24.1
        internal_lb_vip_address: 192.168.0.1
        galera_address: "{{ internal_lb_vip_address }}"

