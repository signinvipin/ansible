# logstash

Installs and starts Logstash 7.17.29.

- Imports the Elastic GPG key and adds the Elastic 7.x yum repository
- Installs `logstash-7.17.29`, then enables and starts the service
- This role is not enabled in `elk_playbook.yml` (the line is commented out). The pipeline config in `templates/` is commented out.
