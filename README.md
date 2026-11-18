# Apple MacBook Performance and Thermal Investigation
## Fedora Linux 45

An independent technical investigation of CPU performance,
thermal behaviour and cooling characteristics on an Apple
MacBook running Fedora Linux.

### Test environment

- Operating system: Fedora Linux 45
- Kernel: Linux 7.3.4
- CPU: Intel Core i5-4260U
- Physical cores: 2
- Logical processors: 4
- CPU base frequency: 1.40 GHz
- Maximum frequency: 2.70 GHz
- Memory: approximately 4 GB
- Power profile: balanced
- CPU governor: schedutil

### Investigation objectives

1. Establish baseline system conditions.
2. Measure idle CPU utilisation.
3. Investigate CPU behaviour under sustained load.
4. Monitor CPU temperatures and fan speed.
5. Examine thermal recovery after CPU stress.
6. Evaluate the effectiveness of the cooling system.

### Key observations

- Idle CPU time: 96.08%
- Initial CPU package temperature: 79 C
- Maximum observed CPU package temperature: 95 C
- Fan speed before stress: 2183 RPM
- Fan speed after stress: 2480 RPM
- Stress test stopped at the configured 95 C safety limit.

### Project structure

results/
  baseline-original.txt
  baseline.txt
  idle-analysis.txt
  long-cpu-stress.txt
  post-stress-cooling.txt
  stress-ng-output.txt

report/
  REPORT.md
  report.html
  performance-report.pdf

DISCLAIMER.md

### Reproducibility

The original measurement outputs are included in the
results directory.

The investigation uses standard Linux monitoring tools,
including stress-ng, lm-sensors and CPU frequency interfaces.

See REPORT.md for methodology, observations and limitations.

### Disclaimer

This is an independent, non-commercial technical investigation.
It is not an Apple-certified benchmark or laboratory test.

See DISCLAIMER.md for the complete disclaimer.

### Author

Independent technical investigation.
