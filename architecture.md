# Architecture

This document describes the system layout, trust boundaries, and design
decisions behind the zero-trust Tailscale exit node implementation.

## Components

### Remote Clients
- Laptops and mobile devices running the Tailscale client
- Authenticated via an identity provider
- Network location alone does not imply trust

### Tailscale Control Plane
- Manages device authentication and key distribution
- Does not carry user traffic
- Compromise does not directly expose application data

### Exit Node (Linux VM)
- Hosted on VMware ESXi
- Performs outbound NAT and IP forwarding
- No inbound services exposed to the public internet

### Edge Router
- No port forwarding configured
- Allows only outbound traffic initiated by the exit node

## Trust Boundaries

- Trust is based on user and device identity, not IP address
- Devices must be explicitly authorized to use the exit node
- The perimeter firewall is not the primary security boundary
- Short-lived keys limit the impact of credential compromise

## Design Decisions

- Exit node chosen over traditional VPN concentrator to minimize attack surface
- Single-purpose Linux VM used for clarity and isolation
- Fail-closed behavior preferred over implicit fallback paths
