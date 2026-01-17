# Traffic Flow

This document explains how traffic moves through the system during normal
operation.

## Normal Operation

1. A remote device authenticates to the Tailscale network.
2. An encrypted WireGuard tunnel is established to the exit node.
3. Internet-bound traffic is routed through the exit node.
4. The exit node performs outbound NAT via the home ISP.
5. Return traffic follows the same encrypted path back to the client.

## Traffic Properties

- End-to-end encryption between client and exit node
- All egress traffic appears to originate from a trusted location
- No inbound connections are initiated toward the internal network

## Split Tunneling Behavior

- Exit node usage is explicitly enabled per device
- Internal Tailscale traffic does not require exit routing
- Default behavior avoids unnecessary traffic redirection
