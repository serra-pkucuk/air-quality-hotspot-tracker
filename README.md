# Air Quality Sensor Network & Hotspot Tracker

**CSE 211 — Data Structures | Yeditepe University | Team project**

A C++17 academic project exploring how sensor readings can be loaded, analyzed for potential air-pollution hotspots, and prioritized for alerts. The intended workflow connects sensor locations, aggregates time-stamped measurements, identifies hotspots, and produces risk-based alerts.

## Technology

- **Language:** C++17
- **Build:** GNU Make, g++
- **Data format:** JSON (`nlohmann/json`)
- **Concepts:** graphs, hash tables, priority queues, file I/O, algorithm integration, and testing

## Architecture

| Component | Responsibility |
| --- | --- |
| `DataLoader` | Read sensor locations and measurements from JSON files |
| Sensor graph and hash map | Represent sensor connectivity and support sensor lookups |
| `HotspotDetector` | Analyze sensor measurements against a configurable threshold |
| `AlertManager` | Assign alert priorities using pollution severity, affected population, duration, and trend |
| Priority queue | Surface high-priority alerts |
| Integration test | Exercise the data-loading, hotspot-detection, and alert workflow |

## Repository structure

```text
.
├── data/                  # Sample sensor data
├── include/core/          # Alert management interface
├── include/utils/         # Data-loading interface
├── src/core/              # Alert management implementation
├── src/utils/             # Data-loading implementation
├── src/main.cpp           # Application entry point
├── tests/integration/     # End-to-end test source
└── Makefile
```

## Build and run

On Linux or another environment with `g++`, GNU Make, and `curl`:

```bash
make deps
make
make run
make test
```

The program also accepts an input path and threshold:

```bash
./build/bin/main data/input_sample.json 100
```

**Repository completeness:** This public snapshot does **not currently include** the headers and implementations for the custom sensor graph, hash map, alert queue, or hotspot detector referenced by `main.cpp`. Accordingly, a clean build of the current repository is not expected to succeed until those modules are added. The commands above document the intended project workflow rather than a verified working build.

## Team and contributions

This was developed as a team assignment. Responsibilities documented by the project:

| Contributor | Area |
| --- | --- |
| Ceyda Şenay | Data structures |
| Hatice Aygan | Time series and memory management |
| Merve Naz Dikme | Algorithms and core logic |
| Irmak Zehra Emri | Interface and visualization |
| **Serra Pehlivanküçük** | **File I/O, testing, and integration** |

My contribution focused on integrating data-loading and testing workflows with the rest of the system. The project was a collaborative academic exercise; credit for the other areas belongs to the respective team members.

## Project status

**Academic project repository — partial source snapshot.** The public files document part of the implementation, but the missing modules must be restored before the application can be built and verified end to end.
