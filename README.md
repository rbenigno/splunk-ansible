Ansible roles and playbooks for Splunk deployment
=================================================

1. Install Splunk binaries as needed:
  - Standard Splunk Install
  - Heavy Forwarder
  - Universal Forwarder
2. Setup syslog-ng for centralized logging:
  - Install and configure syslog-ng.
  - Configure Splunk to monitor the syslog-ng logs.
  - Create cron job to delete old logs.

TODO
----
- [X] The task "Install Splunk Forwarder App" is not idempotent.
- [ ] Fix the {{ splunk_home }} in the splunk_syslog_inputs role.
- [ ] Create a custom sourceytpe for syslog-ng (make sure it works on Universal and Heavy forwarders)
- [ ] Allow send_to_forwarder_app to be loaded from an external source (like the Splunk package).
- [ ] Use cust_vars.yml to define the native Splunk UDP/TCP listeners.
- [ ] Research the correct way to handle the default syslog-ng.conf file (just commenting defaults out now).
- [ ] Only the platform specific splunk_forwarder tasks should be in centos.yml.