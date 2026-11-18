# Apple MacBook Thermal and CPU Performance Investigation

## Fedora Linux 45

Date: 18 November 2026

## 1. Abstract

This investigation examines CPU performance and thermal
behaviour on an Apple MacBook running Fedora Linux 45.

The study includes baseline system measurements, idle
monitoring, CPU stress testing and post-stress cooling
observations.

During the CPU stress test, the processor package temperature
increased from 79 C to 95 C. The test was stopped when the
configured thermal safety threshold was reached.

The results demonstrate the importance of thermal monitoring
when operating older laptop hardware under sustained CPU load.

## 2. Hardware and software environment

Operating system: Fedora Linux 45
Kernel: Linux 7.3.4-300.fc45.x86_64
Processor: Intel Core i5-4260U
Architecture: x86_64
Physical CPU cores: 2
Logical processors: 4
Base frequency: 1.40 GHz
Maximum reported frequency: 2.70 GHz
Memory: approximately 3.7 GiB
Swap: approximately 3.7 GiB zRAM

Power profile: balanced
CPU frequency governor: schedutil

Temperature monitoring used the Linux coretemp and
Apple SMC sensor interfaces.

## 3. Methodology

The investigation consisted of four main stages.

### 3.1 Baseline measurements

System information, CPU configuration, memory utilisation,
power profile, CPU governor, temperature sensors and fan
speed were recorded.

### 3.2 Idle measurements

CPU utilisation and memory pressure were monitored under
relatively idle system conditions.

### 3.3 CPU stress test

A CPU workload was executed using stress-ng with four CPU
workers and a planned duration of 180 seconds.

The test included temperature monitoring and a safety
threshold of 95 C.

The test was stopped when the safety threshold was reached.

### 3.4 Cooling observations

Temperature and fan speed were recorded after the stress
test to examine the beginning of the thermal recovery period.

The available cooling log contains only one sample.

## 4. Baseline observations

The baseline measurements showed:

- CPU package temperature: 79 C
- Exhaust fan speed: 1887 RPM
- CPU frequency scaling governor: schedutil
- Active power profile: balanced
- Available memory: approximately 921 MiB

The recorded CPU temperature was relatively high for a
measurement labelled as baseline.

However, the process list showed background CPU activity,
including browser processes and system services.

Consequently, the baseline should not be interpreted as
a fully unloaded thermal reference.

## 5. Idle test

The idle analysis recorded:

- Average CPU idle: 96.08%
- User CPU: 1.80%
- System CPU: 1.56%
- I/O wait: 0%
- Memory pressure avg10: 0.00%
- zRAM data: 1.1 GiB
- Compressed zRAM: 345.2 MiB
- CPU package temperature: 55 C
- Fan speed: 1202 RPM

The system showed low CPU utilisation during this test.

No significant memory pressure or disk I/O wait was
reported.

## 6. CPU stress test

The CPU stress test was configured as follows:

- Planned duration: 180 seconds
- CPU workers: 4
- Workload: matrixprod
- Temperature safety threshold: 95 C

Initial CPU package temperature: 79 C.

Recorded temperature progression:

79 C
87 C
89 C
91 C
92 C
93 C
94 C
95 C

The temperature threshold was reached approximately
14 seconds after the beginning of the recorded sequence.

The stress test was stopped at the configured safety limit.

The final recorded fan speed was 2480 RPM.

The CPU package temperature reached 95 C, while the
highest recorded individual core temperature was also
95 C.

The stress-ng output reported:

- CPU bogo operations: 27433
- Reported real time: 14.68 seconds
- User time: 56.00 seconds
- System time: 0.13 seconds
- Reported throughput: 1868.15 bogo operations/s
- Failed stressors: 0
- Skipped stressors: 0

The stress-ng process completed successfully from the
tool's perspective. However, the overall planned
180-second test was not completed.

The approximately 14.69-second runtime is consistent
with the safety-limited test sequence.

## 7. Thermal throttling observations

The recorded thermal throttle counters were zero both
before and after the test.

This means that the available counter measurements did
not report an increase in recorded throttling events.

However, zero counters do not conclusively prove that
the processor never experienced thermal or power-related
frequency limitations.

Additional monitoring would be required to establish
the exact throttling behaviour.

## 8. Cooling behaviour

The post-stress cooling measurement began at:

- CPU package temperature: 68 C
- Core 0: 68 C
- Core 1: 68 C
- Fan speed: 2024 RPM

The planned observation period was 60 seconds with
five-second sampling intervals.

Only the first sample is present in the available file.

Therefore, a cooling curve, recovery time or cooling
rate cannot be calculated from the current dataset.

This is an important limitation of the investigation.

## 9. Discussion

The most significant observation is the rapid increase
in CPU temperature under sustained CPU load.

The processor reached 95 C shortly after the stress
test began.

The cooling fan increased its speed from 2183 RPM to
2480 RPM during the recorded stress sequence.

The results indicate that the tested system has limited
thermal headroom under this particular workload and
test environment.

However, the measurements alone cannot establish
whether the behaviour is caused by ageing thermal
paste, dust accumulation, fan condition, heatsink
efficiency, ambient temperature or processor power
management.

The baseline temperature and background process
activity also need to be considered when interpreting
the results.

## 10. Limitations

This investigation has several limitations:

1. Only one hardware configuration was examined.
2. Ambient temperature was not recorded.
3. The exact MacBook model identifier was not included.
4. The baseline included background system activity.
5. The planned three-minute CPU test was stopped early.
6. Cooling recovery data contains only one sample.
7. Thermal throttle counters alone cannot establish
   the complete throttling behaviour.
8. No comparison with another operating system or
   hardware platform was performed.

The findings should therefore be treated as observations
from a single test session rather than universal
performance conclusions.

## 11. Conclusions

The investigation demonstrated that the Apple MacBook
running Fedora Linux 45 was capable of completing the
recorded CPU stress workload without a reported
stress-ng failure.

However, CPU temperature increased rapidly and reached
the configured safety threshold of 95 C.

The fan responded by increasing its rotational speed.

The available data provides useful evidence of the
system's thermal behaviour, but further controlled
measurements would be necessary to evaluate cooling
recovery and sustained performance more accurately.

The investigation also demonstrates the usefulness
of Linux hardware monitoring tools when evaluating
older laptop hardware.

## 12. Reproducibility

The original measurement files are preserved in the
results directory.

Relevant tools and interfaces include:

- stress-ng
- lm-sensors
- sensors
- mpstat
- free
- cpufreq sysfs interfaces
- thermal throttle counters
- Apple SMC sensor interfaces

Any reproduction should use appropriate temperature
monitoring and a conservative safety threshold.

Do not deliberately exceed the processor's thermal
limits.

## 13. Final statement

This project documents an independent investigation
of CPU performance and thermal behaviour on an Apple
MacBook running Fedora Linux 45.

The results are intended for educational and technical
reference purposes.

See DISCLAIMER.md.
