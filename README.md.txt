# eBPF Kernel Zero-Trust Runtime Threat Monitor

![Python 3](https://img.shields.io/badge/Language-Python%203.10-blue)
![Cybersecurity](https://img.shields.io/badge/Domain-Kernel%20Security%20%26%20eBPF-red)
![Developer](https://img.shields.io/badge/Developer-Ayoub%20Lahmar-brightgreen)

A kernel-level zero-trust telemetry engine utilizing Extended Berkeley Packet Filters (eBPF) and information theory metrics to detect runtime process injection and encrypted shellcode execution.

Implemented by **Ayoub Lahmar** ([@Redayoub-lang](https://github.com/Redayoub-lang)).

## 📐 Mathematical Formulation

Payload obfuscation and encryption detection relies on Shannon Entropy \(H(X)\) over byte frequency distributions \(P(x_i)\):

$$
H(X) = -\sum_{i=1}^{n} P(x_i) \log_2 P(x_i)
$$

An anomaly trigger is dispatched when \(H(X) > \tau_{\text{threshold}}\), flagging byte streams exhibiting uniform distribution typical of encrypted payloads.

## 💻 Build & Run

```bash
python kernel_monitor.py