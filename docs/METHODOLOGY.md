# Research Methodology

## Project
Apple MacBook Air 6,2 – CPU Performance and Thermal Investigation

Research ID: 001
Test date: 18 November 2026
Operating system: Fedora Linux 45

## 1. Experimental Environment

Hardware:
- Apple MacBook Air 6,2
- Intel Core i5-4260U
- 2 physical cores / 4 logical processors
- 4 GB RAM
- Apple SSD SD0128F

Software:
- Fedora Linux 45
- Linux kernel 7.3.4-300.fc45.x86_64
- stress-ng
- lm-sensors
- Linux CPU frequency interfaces

## 2. Measurement Categories

### Baseline
System configuration, processor information, memory,
power profile, CPU governor, temperatures and fan speed.

### Idle
CPU utilisation, memory pressure, zRAM utilisation,
temperature and fan speed.

### CPU Stress
A stress-ng CPU workload using four workers.
The planned workload duration was 180 seconds.

A temperature safety threshold of 95 °C was configured.

The workload was stopped when this threshold was reached.

### Cooling Observation
Temperature and fan speed were recorded after the stress test.

The available original file contains one sample.
It does not provide a complete cooling recovery curve.

## 3. CPU Frequency Measurements

CPU frequency values were recorded at selected points
during the stress test.

These are instantaneous observations, not continuous
frequency measurements.

They cannot independently establish the presence or
absence of thermal throttling.

## 4. Thermal Throttling Measurements

Linux thermal throttle counters were inspected before
and after the stress test.

No counter increments were recorded.

This observation does not rule out all forms of
thermal or power-related performance limitation.

## 5. Data Integrity

Original measurement files are preserved separately.

The archive directory contains copies of the original
measurement files.

SHA-256 checksums were generated to support file integrity
verification.

The files baseline.txt and baseline-original.txt have
identical SHA-256 checksums.

## 6. Experimental Limitations

- Ambient temperature was not recorded.
- Background processes were active during baseline sampling.
- The stress workload ended before its planned duration.
- CPU frequency was not sampled continuously.
- Only one cooling observation is available.
- No independent laboratory instrumentation was used.
- No comparative operating system test was performed.

## 7. Reproducibility

Future investigations should record:
- Exact commands and tool versions.
- Ambient temperature.
- Continuous CPU frequency.
- CPU package and core temperatures.
- Fan speed.
- Workload duration.
- Power profile.
- Complete cooling recovery measurements.

Future measurements must be stored separately from
the original 18 November 2026 dataset.
