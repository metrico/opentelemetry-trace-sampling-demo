<img src="https://docs.checkmk.com/latest/images/grafana_logo.png" height=100>&nbsp;&nbsp;<img src="https://user-images.githubusercontent.com/1423657/168049484-fa30a5e5-c9fc-41e1-a347-9c0e71e2c5a6.png" height=100><img src="https://user-images.githubusercontent.com/1423657/168049396-54f232d0-ba68-4b05-81bb-b086e3933394.png" height=110>




# Grafana + Uptrace/cLoki
This repository hosts a [ClickHouse](https://clickhouse.com) centric alternative recipe for the Grafana [blog post](https://grafana.com/blog/2022/05/11/an-introduction-to-trace-sampling-with-grafana-tempo-and-grafana-agent/?mdm=social&utm_source=li&utm_medium=social) on Grafana Agent's tail sampling functionality

The repository features a Docker Compose file that includes:

- [Grafana](https://grafana.com/) (visualizes data)
- [Grafana Agent](https://grafana.com/docs/agent/latest/configuration/?src=li&mdm=social) (processes trace data)
- [uptrace](https://uptrace.dev) (inserts and queries traces)
- [cLoki](https://cloki.org) (inserts and queries logs)
- [ClickHouse](https://clickhouse.com) (sotres data)

A demo application to show trace sampling, which:
- Sends traces to Grafana Agent
- Logs directly to cLoki


## Running

Ensure you have both Docker and Docker Compose installed, and then in a terminal simply run:
```bash
docker-compose up
```
This will stand up all the required components

- Access uptrace & cloki APIs through Grafana at [http://localhost:3000/](http://localhost:3000/)
- Access uptrace directly at [http://localhost:14318/](http://localhost:14318/)
- Access cloki directly at [http://localhost:3100/](http://localhost:14318/)

Follow the Grafana [blog post](https://grafana.com/blog/2022/05/11/an-introduction-to-trace-sampling-with-grafana-tempo-and-grafana-agent/?mdm=social&utm_source=li&utm_medium=social)

![image](https://user-images.githubusercontent.com/1423657/168690283-b0912a90-7503-4b4f-9ac7-e6b76c1460d1.png)


