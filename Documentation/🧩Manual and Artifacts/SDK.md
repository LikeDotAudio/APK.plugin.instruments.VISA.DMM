# SDK — INSTRUMENT.DMM

Every DMM model this library drives, and how to drive it. Each model answers the same five verbs over HTTP (its own port), WebSocket, a Unix socket and the bus; one page per model below lists its routes and every command.

← [Manual and Artifacts](INDEX.md)

| Verb | What it does |
|---|---|
| `get` | reads one value |
| `set` | writes one value |
| `nab` | reads more than one thing (observation, telemetry) |
| `rig` | configures several arguments at once |
| `do` | executes an action; takes no value |

| Model | Maker | get | set | nab | rig | do | Port |
|---|---|---:|---:|---:|---:|---:|---:|
| [2000](SDK/2000.md) | Keithley | 71 | 42 | 73 | 4 | 33 | 15400 |
| [34401A](SDK/34401A.md) | HP / Agilent / Keysight | 71 | 42 | 74 | 4 | 33 | 15401 |
| [34410A](SDK/34410A.md) | HP / Agilent / Keysight | 71 | 42 | 73 | 4 | 33 | 15402 |
| [34411A](SDK/34411A.md) | HP / Agilent / Keysight | 71 | 42 | 73 | 4 | 33 | 15403 |
| [34420A](SDK/34420A.md) | HP / Agilent / Keysight | 71 | 42 | 73 | 4 | 33 | 15404 |
| [34450A](SDK/34450A.md) | HP / Agilent / Keysight | 71 | 42 | 73 | 4 | 33 | 15405 |
| [34460A](SDK/34460A.md) | HP / Agilent / Keysight | 71 | 42 | 73 | 4 | 33 | 15406 |
| [34461A](SDK/34461A.md) | HP / Agilent / Keysight | 71 | 42 | 73 | 4 | 33 | 15407 |
| [34465A](SDK/34465A.md) | HP / Agilent / Keysight | 71 | 42 | 73 | 4 | 33 | 15408 |
| [34470A](SDK/34470A.md) | HP / Agilent / Keysight | 71 | 42 | 73 | 4 | 33 | 15409 |
| [3458A](SDK/3458A.md) | HP / Agilent / Keysight | 71 | 42 | 73 | 4 | 33 | 15410 |
| [DM3058](SDK/DM3058.md) | Rigol | 71 | 42 | 73 | 4 | 33 | 15411 |
| [DM3068](SDK/DM3068.md) | Rigol | 71 | 42 | 73 | 4 | 33 | 15412 |
| [DMM6500](SDK/DMM6500.md) | Keithley | 71 | 42 | 73 | 4 | 33 | 15413 |
| [U1272A](SDK/U1272A.md) | HP / Agilent / Keysight | 71 | 42 | 73 | 4 | 33 | 15414 |
