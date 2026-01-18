# Macro Risk Monitoring System

Distributed Raspberry Pi–based system for macroeconomic data collection,
risk indicator generation, and scenario analysis, with integrated physical
instrumentation for deterministic and stochastic stress testing.

## Hardware Architecture

- Pi 5 — Compute / scenario engine
- Pi 4 — Data storage, validation, persistence
- Pi Zero 1–4 — Data collectors
- Pico 1–4 — Physical instrumentation & stress injection

## Instrumentation Tier (Pico Controllers)

The system includes a dedicated instrumentation layer implemented on
Raspberry Pi Pico microcontrollers. These devices generate exogenous,
physically triggered signals used for system validation, stress testing,
and latency measurement.

- Pico-01 — Heartbeat monitor (system liveness)
- Pico-02 — Stress trigger (manual or stochastic shock events)
- Pico-03 — Risk indicator light (physical regime signaling)
- Pico-04 — Latency probe (end-to-end response timing)

## Deployment Model

Deployment is **micro-based**: devices pull only the code relevant to their
assigned role. No device depends on another for boot or recovery.

This design emphasizes:
- fault isolation
- auditability
- reproducibility
- controlled stress experimentation
