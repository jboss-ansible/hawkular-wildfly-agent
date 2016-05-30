Deploy Hawkular agent on an existing Wildfly Server
===================================================

This role allows to automatically instrument an exiting Wildfly to report to Hawkular Services.

Requirements
------------

This role suppose that a Wildfly server is already installed with the default file structure and a user is allowed to edit the files.

Role Variables
--------------

# Generic variables
download_directory: /tmp

# Hawkular Services server variables
hawkular_server_username: jdoe
hawkular_server_password: Password0_
hawkular_server_url: http://localhost:8080

# Wildfly variables
wildfly_home_dir: /opt/wildfly-10.0.0.Final
wildfly_user: wildfly

# Agent variables
## If you want to use the fully customized subsystem role file, set this to true
## and make sure the role file "subsystem-snippet.xml" is configured
hawkular_wildfly_agent_use_subsystem_snippet: false
## For the agent to autogenerate its own feed ID, set this to an empty value
hawkular_wildfly_agent_feed_id:
## If the agent is to run in metrics only mode, a tenant ID must also be set
hawkular_wildfly_agent_metrics_only: "false"
hawkular_wildfly_agent_tenant_id:
Dependencies
------------

None

Example Playbook
----------------

- hosts: localhost
  remote_user: root
  roles:
    - deploy-hawkular-wildfly-agent

License
-------

Apache License v2

Author Information
------------------

Heiko Rupp, John Mazzitelli, Thomas Heute - Red Hat
