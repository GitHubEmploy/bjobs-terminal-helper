# BJ Services — Terminal Helper Utility

Java Swing GUI wrapper for the IBM LSF `bjobs` command on CentOS/RHEL systems. Displays real-time batch job status in a refreshable desktop window.

## Features

- **Real-Time Monitoring** — Auto-refreshes `bjobs` output every 1 second
- **Swing GUI** — Clean desktop window with scrollable output area
- **Zero Dependencies** — Uses only standard Java libraries

## Tech Stack

| Component | Technology |
|-----------|------------|
| Language | Java (JDK 8+) |
| UI | Swing (`JFrame`, `JTextArea`) |
| OS | CentOS / RHEL with IBM LSF |

## Project Structure

```
BjobsApp.java   — Main application (Swing GUI + ProcessBuilder)
run.sh          — Compile & run script
ignorethis.java — Scratch / test file
```

## Usage

```bash
./run.sh
```

Or manually:

```bash
javac BjobsApp.java
java BjobsApp
```

The application runs `bjobs` via `ProcessBuilder`, reads stdout, and displays it in a `JTextArea`. The output refreshes automatically every second using a `ScheduledThreadPoolExecutor`.

## Notes

Requires IBM LSF (Load Sharing Facility) and the `bjobs` command available on the system PATH. Designed for CentOS environments.
