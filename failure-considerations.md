# Failure Considerations

This document outlines expected failure modes and the system’s behavior
under degraded conditions.

## Exit Node Failure

- Remote clients lose exit-node-based internet access
- No automatic fallback to insecure paths occurs
- Failure is immediately visible to the user

## Identity Revocation

- Device or user access can be revoked centrally
- Existing tunnels expire automatically
- No firewall or routing changes are required

## Control Plane Unavailability

- Existing tunnels may continue temporarily
- New device authentication is blocked
- No exposure of internal services occurs

## Design Tradeoffs

- High availability for the exit node is not implemented
- Security and simplicity are favored over redundancy
- Fail-closed behavior is intentional
