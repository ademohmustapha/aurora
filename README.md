# AURORA — Autonomous Unified Resilience & Organizational Real-time Awareness
### Production Release

> Predict. Evolve. Contain. Align. Govern.

AURORA is a **seven-layer autonomous cyber resilience platform** that goes beyond detection — it predicts threats before they materialise, evolves its own detection rules, aligns human decision-making in real time, and contains breaches across entire supply chains.

---

## Architecture: Seven Layers

| # | Layer | Engine | Core Algorithm |
|---|-------|--------|----------------|
| 1 | **Identity & Trust** | Zero Trust Fabric | Bayesian trust decay · Behavioral biometrics · Adaptive MFA |
| 2 | **Org Intelligence** | SOIN-X | AES-256-GCM vault · HMAC audit chain · Crisis mode |
| 3 | **Human Risk** | AURIX | IsolationForest (real sklearn) · Digital Twin · Mahalanobis drift |
| 4 | **Containment** | NEXUS-SHIELD | NetworkX BFS blast radius · 8-level action matrix · <30s SLA |
| 5 | **Alignment** | ECLIPSE-X | Bayesian intent scoring · Kahneman nudge theory · Decision Co-Pilot |
| 6 | **Supply Chain** | Cascade Engine | Monte Carlo 300 runs · NetworkX PageRank · ε-DP federation |
| 7 | **Evolution** | Threat Cognition | Real genetic algorithm (F1-scored) · Noisy-OR Bayesian · 200-run Monte Carlo |

---

## Quick Start

```bash
# 1. Clone and install
git clone https://github.com/ademohmustapha/aurora
cd aurora
pip install -r requirements.txt

# 2. Run
python3 aurora.py               # Interactive menu
python3 aurora.py doctor        # Self-diagnostics
python3 aurora.py risk --user alice@corp.com
python3 aurora.py horizon       # Predictive event horizon
python3 aurora.py evolve        # Run co-evolution cycle
python3 aurora.py api           # REST API on port 9100

# 3. Docker
docker build -t aurora .
docker run -v aurora-data:/home/aurora/.aurora -p 9100:9100 aurora
```

---

## What Is Real vs What Is Simulated

AURORA is honest about what each engine does.

| Engine | Status | What it actually does |
|--------|--------|-----------------------|
| IsolationForest (HRI) | ✅ **Real sklearn** | Trained on per-actor 30-event rolling window |
| Genetic Algorithm | ✅ **Real GA** | F1-scored fitness, tournament selection, elitism, disk-persisted genome |
| Monte Carlo (Event Horizon) | ✅ **Real 200 runs** | Holt-Winters + stochastic forward simulation |
| Monte Carlo (Supply Chain) | ✅ **Real 300 runs** | Stochastic BFS propagation per edge criticality |
| NetworkX BFS (Blast Radius) | ✅ **Real graph BFS** | Loads real topology; falls back to heuristic if no graph loaded |
| PageRank (Supply Chain) | ✅ **Real nx.pagerank** | Applied when dependency graph is built |
| Mahalanobis drift (Digital Twin) | ✅ **Real computation** | Trajectory variance vs recent window |
| Differential Privacy | ✅ **Real Laplace/Gaussian** | Dwork & Roth (2014) mechanisms |
| Federated Learning | ✅ **Real FedAvg** | McMahan et al. (2017) |
| Quantum KEM | ⚠️ **Simulation** | SHA3+PRG interface; real roundtrip verified. Swap for liboqs when available. |
| Ethics Engine | ✅ **Real 5-pillar eval** | Deontological + proportionality + consequentialist + bias + privacy |

---

## Deployment Modes

| Mode | Command | Use case |
|------|---------|----------|
| Standalone | `python3 aurora.py` | Single-org evaluation |
| API Server | `python3 aurora.py api` | Integration with SIEM/SOAR |
| Docker | `docker run aurora` | Containerised production |
| Docker Compose | `docker-compose up` | Full stack with persistent storage |

---

## API Reference (Port 9100)

```
POST /risk           — Compute Human Risk Index
POST /contain        — Trigger containment action
GET  /horizon        — Predictive threat horizon
POST /evolve         — Run co-evolution cycle
GET  /supply-chain   — Supply chain risk heatmap
GET  /health         — Platform health check (unauthenticated)
```

Authentication: `X-Aurora-Token: <token>` header required on all endpoints except `/health`.

---

## Ethics & Governance

Every autonomous action passes through a **5-pillar ethics engine**:

1. **Deontological** — Hard rules (no medical data without consent, no mass surveillance)
2. **Proportionality** — Action severity must not exceed risk × 1.5
3. **Privacy Impact** — High-privacy actions require consent/legal basis
4. **Bias Guard** — Flags actors receiving >3× average intervention rate
5. **Consequentialist** — Expected benefit must justify intervention

Humans can **always override** any autonomous decision. All overrides are logged immutably.

---

## Compliance

| Framework | Status |
|-----------|--------|
| GDPR | Structured rule evaluation — purpose limitation, consent, data minimisation |
| SOC 2 | Availability, confidentiality, integrity, access control checks |
| HIPAA | PHI protection, minimum necessary, always-on audit logging |
| ISO 27001 | Access control policy, cryptographic controls, supplier relationship checks |

---

## Security Hardening

- Rate limiting: token bucket (100 req/60s per client)
- Input sanitization: SQL injection, command injection, path traversal, prompt injection
- Constant-time token comparison (timing attack prevention)
- Tamper-evident HMAC-chained audit log
- Non-root Docker user (UID 10001)
- tini as PID 1 (correct SIGTERM handling)
- Memory wiping on sensitive bytearray deallocation
- Ed25519 identity keys, X25519 key exchange, AES-256-GCM encryption

---

*AURORA — Built by Ademoh Mustapha Onimis*
