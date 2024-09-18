# Node.js Cluster Implementation

The server forks a worker for each CPU core, allowing parallel handling of requests.


## Features
- **Primary Process:** The main process spawns worker processes based on the number of CPU cores available.
- **Worker Processes:** Each worker serves incoming requests, with the ability to perform computationally intensive tasks.
- **Auto-Restart Workers:** If a worker crashes, a new one is automatically spawned to maintain performance.

## How It Works
1. **Primary Process**: 
   - Forks a worker for each available CPU core.
   - Logs the number of CPUs and monitors workers.
   - Automatically restarts workers if they crash.

2. **Worker Processes**: 
   - Serve two routes:
     - `"/"`: Returns a "Hello World!" message.
     - `"/api/:n"`: Computes the sum of numbers up to `n` (capped at 5 billion).


