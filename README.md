<img src="https://user-images.githubusercontent.com/1423657/168049484-fa30a5e5-c9fc-41e1-a347-9c0e71e2c5a6.png" height=100><img src="https://user-images.githubusercontent.com/1423657/168049396-54f232d0-ba68-4b05-81bb-b086e3933394.png" height=120>




# Grafana + Uptrace + cLoki
This repository hosts an open-source alternative recipe for the Grafana [blog post](https://grafana.com/blog/2022/05/11/an-introduction-to-trace-sampling-with-grafana-tempo-and-grafana-agent/?mdm=social&utm_source=li&utm_medium=social) on Grafana Agent's tail sampling functionality, using [uptrace](https://uptrace.dev) and [cLoki](https://cloki.org) on top of [ClickHouse](https://clickhouse.com)


The repository includes:
* A simple application that mimics a service receiving and responding to API requests, which sends logs directly to a local cLoki instance.
* A configuration for Grafana Agent that receives traces in OTLP format and sends them to a local Uptrace instance.
* Two pre-provisioned data sources for Grafana.
* A Docker Compose file used to stand up a local demonstration environment, comprised of:
  * Demo sender application
  * Grafana Agent
  * Grafana
  * Uptrace
  * cLoki
  * ClickHouse

## Running

Ensure you have both Docker and Docker Compose installed, and then in a terminal simply run:
```bash
docker-compose up
```
This will stand up all the required components

- Access uptrace & cloki APIs through Grafana at [http://localhost:3000/](http://localhost:3000/)
- Access uptrace directly at [http://localhost:14318/](http://localhost:14318/)
- Access cloki directly at [http://localhost:3100/](http://localhost:14318/)

