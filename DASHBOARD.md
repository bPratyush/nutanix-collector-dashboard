# Nutanix Collector Dashboard

Produced end-to-end by an MCP Playground workflow wiring six MCP servers:

1. collector - reads collected Prism SQLite data over a REST API.
2. chart (AntV) - renders unit-scaled line and donut charts, returning image URLs.
3. filesystem - persists the chart URLs locally.
4. everything - echoes milestones and sums the cluster's used + free storage.
5. memory - builds a cluster -> host -> vm knowledge graph.
6. github - creates this repo, commits the artifacts, and opens this pull request.

## Contents

- `charts/*.url.txt` - one AntV image URL per chart (open in a browser to view):
  - `cluster-line.url.txt` - cluster performance over time (%)
  - `cluster-storage-pie.url.txt` - cluster storage used vs free
  - `cluster-memory-pie.url.txt` - cluster memory used vs free
  - `host-line.url.txt` - host performance over time (%)
  - `host-storage-pie.url.txt` - host storage used vs free
  - `vm-line.url.txt` - VM performance over time (%)
  - `clusters-storage-pie.url.txt` - storage across all clusters
  - `containers-consumed-pie.url.txt` - storage container consumption
- `knowledge-graph.json` - the cluster/host/vm knowledge graph, with the chart URLs attached as observations.

> Charts are hosted image URLs (not committed images), so they are stored as `.url.txt` files rather than embedded inline.
