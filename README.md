Role Name
=========

Role installs vDVS driver in ESX host. This driver is used by vDVS docker plugin to setup persistent storage for container.
More info:

Persistent storage for a Docker Swarm
[vDVS docs](vmware.github.io/docker-volume-vsphere/documentation/)

Requirements
------------
Role requires vib file to be available for download. It expects it at location on Artifactory

Role Variables
--------------

`artifactory`: defines url root of artifactory service
`vdvs_datastore`: defines where vDVS should keep its db file. Db is used to implement vmgroup concept. [Read more](http://vmware.github.io/docker-volume-vsphere/documentation/admin-cli.html#vmgroup)
`vib_name`: name of vib file. This is binary file that contains driver and will be installed in ESX
`force_update`: It may happen compar_version filter doesn't work so you can use this variable to force the update


Example Playbook
----------------

    - hosts: esx
      roles:
         - { role: ansible-role-vdvs-esx }

License
-------

BSD

Author Information
------------------

EIS EngOps Team
