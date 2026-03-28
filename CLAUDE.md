# Nvidia Tool

## Purpose
Collects NVIDIA GPU performance metrics (utilization, temperature, memory, power) during benchmark execution using the NVIDIA Management Library (pynvml).

## Language
Python 3 — collection and post-processing scripts

## Key Files
| File | Purpose |
|------|---------|
| `nvidia-collect` | Initializes pynvml, collects GPU metrics at intervals |
| `nvidia-start` | Launches nvidia-collect in background |
| `nvidia-stop` | Stops collection, compresses output with xz |
| `nvidia-post-process` | Parses collected data into crucible metrics (uses `toolbox.metrics` from `$TOOLBOX_HOME/python`) |
| `rickshaw.json` | Rickshaw integration: endpoint allow/block lists, file deployment, post-process script |
| `workshop.json` | Engine image build: requires pynvml |

## Conventions
- Primary branch is `main`
- Runs as a profiler tool on master/worker/profiler/compute roles, blocked on client/server
- Requires NVIDIA GPUs and drivers on the target host
