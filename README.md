# COMP4601 Design Project B — Silicon Pulse

## What We're Building

We're building a real-time cardiac arrhythmia detection system on the **Kria KV260 FPGA board**. The idea is to take a live ECG signal, run it through the Pan-Tompkins QRS detection pipeline, and classify each heartbeat as normal or arrhythmic — all at the edge, in real time.

The Pan-Tompkins filter chain (the compute-heavy part) gets accelerated in the FPGA's programmable logic using Vivado HLS, while a small fixed-point neural network handles the final beat classification. We'll be comparing latency, throughput and energy consumption against a pure software baseline running on the board's ARM processor.

Dataset: [MIT-BIH Arrhythmia Database](https://physionet.org/content/mitdb/) (open access, PhysioNet)

---

## The Team

**Team Name:** Silicon Pulse

| Name | Student ID | Role |
|------|-----------|------|
| Netik Kumar Maheshwari | z5636903 | Team Representative |
| Rukshaar Aujla | — | Team Member |
| Venus | — | Team Member |
| Esha Tiwari | — | Team Member |

---

## Contact

For any questions or correspondence regarding this project, please reach out to our team representative:

**Netik Kumar Maheshwari**  
📧 z5636903@ad.unsw.edu.au

---

## Repository Structure

```
├── sw/             # C/C++ software implementation (Pan-Tompkins + MLP)
├── hls/            # Vivado HLS kernel source + testbenches
├── ps_driver/      # ARM PS driver code (AXI-Stream, AXI-Lite)
├── python/         # MLP training, weight quantisation scripts
├── data/           # Sample ECG records (MIT-BIH subset)
├── docs/           # Reports, project plan, presentation slides
└── README.md
```

> This repository will be updated progressively through Weeks 3–10 of the 2026 COMP4601 session.
