<img src="https://user-images.githubusercontent.com/1423657/173144443-fc7ba783-d5bf-47f9-bf59-707693da5ed1.png" height=140><img src="https://docs.checkmk.com/latest/images/grafana_logo.png" height=100>




# Grafana + qryn
This repository hosts a [ClickHouse](https://clickhouse.com) centric alternative for the Grafana [blog post](https://grafana.com/blog/2022/05/11/an-introduction-to-trace-sampling-with-grafana-tempo-and-grafana-agent/?mdm=social&utm_source=li&utm_medium=social) on tail sampling functionality

💡 _Uptrace and cLoki APIs are transparently compatible with Grafana Loki and Tempo APIs_ 

📦 The repository features a Docker Compose file that includes:

- [Grafana](https://grafana.com/) _(visualizes data)_
- [Grafana Agent](https://grafana.com/docs/agent/latest/configuration/?src=li&mdm=social) _(processes trace data)_
- [qryn](https://cloki.org) _(inserts and queries logs, metrics, telemetry)_
- [ClickHouse](https://clickhouse.com) _(sotres data)_

A demo application to show trace sampling, which:
- Sends traces to Grafana Agent
- Logs directly to cLoki


## Running

Ensure you have both Docker and Docker Compose installed, and then in a terminal simply run:
```bash
docker-compose up
```
This will stand up all the required components

- Access qryn LogQL and Tempo APIs through Grafana at [http://localhost:3000/](http://localhost:3000/)
- Access cloki directly at [http://localhost:3100/](http://localhost:14318/)

## Usage

Follow the Grafana [blog post](https://grafana.com/blog/2022/05/11/an-introduction-to-trace-sampling-with-grafana-tempo-and-grafana-agent/?mdm=social&utm_source=li&utm_medium=social)

Two data sources have been pre-provisioned: Tempo and Loki. Loki contains log output from the demo app — including trace IDs — and Tempo is storing the traces. At the start, all of the traces being emitted from the demo app are being stored. We can quickly verify that by going to the Explore page in Grafana and looking at all of the logs.

![image](https://user-images.githubusercontent.com/1423657/168691275-3039fb8e-4d4c-48b0-a9b8-0baaf84f8f69.png)

Let’s look at some traces by expanding some of the loglines:

![image](https://user-images.githubusercontent.com/1423657/168691286-2dde09da-6c25-42de-b680-3fb7e77280d8.png)

Use the `Tempo` derived field link to access the traces:

![image](https://user-images.githubusercontent.com/1423657/168691293-2b45f9ad-7424-4351-9d02-5bbb885324d2.png)

Using the Tempo Beta Search functionality we can find spans that have the appropriate status code set:

![image](https://user-images.githubusercontent.com/1423657/168690283-b0912a90-7503-4b4f-9ac7-e6b76c1460d1.png)

------------

### Disclaimer

- All rights belong to their respective owners
- Grafana®, Loki™ and Tempo® are a Trademark of Raintank, Grafana Labs. ClickHouse® is a trademark of ClickHouse Inc.
