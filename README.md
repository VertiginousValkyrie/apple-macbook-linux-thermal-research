Apple MacBook Performance and Thermal Investigation

Platform: Apple MacBook
Operating System: Fedora Linux 45

An independent technical investigation into CPU performance, thermal behaviour, and cooling response on an Apple MacBook running Fedora Linux.

The purpose of this project is to understand how Linux manages processor performance and temperature on Apple hardware through practical testing, system monitoring, and analysis of recorded measurements.

Test Environment
Component	Specification
Manufacturer	Apple
Computer model	Not yet documented
Hostname	Not yet documented
Operating system	Fedora Linux 45
Kernel	Linux 7.3.4
CPU	Intel Core i5-4260U
Physical cores	2
Logical processors	4
CPU base frequency	1.40 GHz
Maximum frequency	2.70 GHz
Memory	Approximately 4 GB
Power profile	Balanced
CPU governor	schedutil
Investigation Objectives

The investigation focuses on the following areas:

Establishing baseline system conditions.
Observing CPU utilisation under idle conditions.
Investigating processor behaviour under CPU stress.
Monitoring CPU temperatures and fan speed.
Recording post-stress thermal conditions.
Examining how Linux reports and manages thermal behaviour.
Key Observations

The following values were recorded during the original test session.

Measurement	Observed value
Idle CPU time	96.08%
Initial CPU package temperature	79 °C
Maximum observed CPU package temperature	95 °C
Fan speed before stress	2183 RPM
Fan speed after stress	2480 RPM

The stress test was stopped when the configured temperature threshold of 95 °C was reached.

The initial CPU temperature was already relatively high. Background system activity was also present during the initial observations, so these conditions should not be interpreted as a clean idle baseline.

Measurement Limitations

This investigation represents an initial experimental test session rather than a comprehensive hardware benchmark.

Important limitations include:

Measurements were collected from a single test system.
The initial system temperature was relatively high.
Background processes affected the initial CPU utilisation measurements.
The thermal recovery measurement does not provide a continuous cooling curve.
Repeated stress tests and comparative measurements have not yet been completed.
The results do not establish the overall cooling performance of all Apple MacBook models.

These limitations are documented to distinguish measured observations from conclusions that would require further testing.

Project Structure
text
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

Reproducibility

The original measurement outputs are included in the results/ directory.

The investigation uses standard Linux monitoring and testing tools, including:

stress-ng
lm-sensors
Linux CPU frequency interfaces

See REPORT.md for the detailed methodology, measurements, observations, and limitations.

Future Work

Planned improvements and further investigations include:

Repeated CPU stress measurements.
Continuous CPU frequency and temperature monitoring.
More detailed thermal recovery measurements.
Additional investigation of Linux CPU frequency scaling and thermal management.
Improved documentation of the hardware and test environment.
Disclaimer

This is an independent, non-commercial technical investigation conducted for educational and research purposes.

It is not an Apple-certified benchmark or a controlled laboratory study.

See DISCLAIMER.md for the complete disclaimer.

Author

Independent technical investigation by VertiginousValkyrie.
