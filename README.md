OpenShift 4 Load Balancer for Qubinode
=========

This role will create a OpenShift 4 Load balancer for the Qubinode project.
This load balancer will manage the using pass-through mode the Kubernetes API (tcp/6443), Machine Server Config (tcp/22623) and the OPenShift Routers HTTP and HTTPS (tcp/80, tcp/443).

Reference Load Balancer Configuration  
Port | Machines  | Internal  | External  | Description  |   |  
---|---|---|---|---|---|--  
6443 | Bootstrap and control plane. You remove the bootstrap machine from the load balancer after the bootstrap machine initializes the cluster control plane. |  :heavy_check_mark:  |   :heavy_check_mark: |  Kubernetes API server |   |  
22623 |  Bootstrap and control plane. You remove the bootstrap machine from the load balancer after the bootstrap machine initializes the cluster control plane. |   :heavy_check_mark: |   |  Machine Config server |   |  
443 | The machines that run the Ingress router pods, compute, or worker, by default.  |  :heavy_check_mark:  | :heavy_check_mark:  | HTTPS traffic  |   |  
80  | The machines that run the Ingress router pods, compute, or worker by default.  | :heavy_check_mark: | :heavy_check_mark:  | HTTP Traffic  |   |  

[NETWORK TOPOLOGY REQUIREMENTS](https://docs.openshift.com/container-platform/4.2/installing/installing_bare_metal/installing-bare-metal.html#installation-network-user-infra_installing-bare-metal)  

Requirements
------------  
- Ansible
- podman
- buildah
- skopeo

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD


Acknowledgments
------------------
Robert Bohne - [rbo](https://github.com/rbo)

Author Information
------------------

Tosin Akinosho - [tosin2013](https://github.com/tosin2013)  
Rodrique Heron - [flyemsafe](https://github.com/flyemsafe) 
