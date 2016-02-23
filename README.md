Install syslog-ng server with Splunk Universal Forwarder
========================================================

Install and configure syslog-ng for centralized logging, and Splunk Universal Forward to monitor the syslog-ng logs.  Includes a cron job to delete old logs.

TODO
----
- [X] The task "Install Splunk Forwarder App" is not idempotent.
- [ ] Allow send_to_forwarder_app to be loaded from an external source (like the Splunk package).
- [ ] Use cust_vars.yml to define the native Splunk UDP/TCP listeners.
- [ ] Research the correct way to handle the default syslog-ng.conf file (just commenting defaults out now).
- [ ] Only the platform specific splunk_forwarder tasks should be in centos.yml.