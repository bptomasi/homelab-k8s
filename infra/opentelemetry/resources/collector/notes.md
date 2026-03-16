
The structure of any Collector configuration file consists of four
classes of pipeline components that access telemetry data:
- receivers
- processors
- exporters
- connectors

After each pipeline component is configured you must enable it using
the pipelines within the service section of the configuration file.

---

The Host Metrics receiver generates metrics about the host system
scraped from various sources and host entity event as log. **This is
intended to be used when the collector is deployed as an agent**.


