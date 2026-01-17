# Zero‑Trust Remote Access with a Tailscale Exit Node

This project documents a zero‑trust remote access design using a Linux‑based
Tailscale exit node hosted on VMware ESXi.

The goal is to provide secure, identity‑based outbound access to the internet
from any authorized device **without exposing inbound services on the edge
router**.

Rather than relying on traditional VPNs or port forwarding, this design
leverages WireGuard‑backed tunnels and identity‑aware access controls.

---

## Objectives

- Enable secure remote browsing through a trusted home ISP
- Eliminate inbound firewall exposure on the edge router
- Enforce identity‑based access instead of network‑based trust
- Integrate cleanly with an existing ESXi‑based infrastructure

---

## Key Outcomes

- All remote traffic egresses through a controlled exit node
- No inbound ports are opened on the perimeter firewall
- Access is tied to user and device identity, not IP address
- Revoking access is immediate and centralized

---

## Scope

This project focuses on **architecture, trust boundaries, and failure behavior**.
It intentionally avoids step‑by‑step installation instructions.

---

## Contents

- `architecture.md` — system layout and trust boundaries
- `traffic-flow.md` — how traffic moves through the system
- `failure-considerations.md` — what happens when components fail
