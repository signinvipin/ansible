# kibana

Installs and starts Kibana 7.17.29.

- Adds the Elastic 7.x yum repository
- Installs `kibana-7.17.29`
- Sets `server.host: 0.0.0.0` in `/etc/kibana/kibana.yml` so Kibana is reachable from other hosts
- Enables and starts the service
