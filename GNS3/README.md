# GNS3 Virtualization Lab

## Objective
Set up GNS3 in a virtualized environment to simulate network topologies and integrate with Wireshark for packet analysis.

## Setup Steps
1. Enable virtualization in BIOS (VT-d).
2. Install VMware Workstation Pro.
3. Deploy GNS3 VM.
4. Configure network adapters and test connectivity.

## Screenshots
- ![Screenshot 1](./screenshots/setup.png)
- ![Screenshot 2](./screenshots/topology.png)

## Configurations
- Example config files stored in `./configs/`.

## Scenario
- Simulated a 3-router topology with OSPF.
- Captured traffic using Wireshark for protocol analysis.

## Reflection
- Learned how to integrate GNS3 with Wireshark for real-time packet capture.
- Faced challenges with adapter bridging, solved by adjusting VMware network settings.
- Relevant to NOC/Cloud roles: demonstrates troubleshooting and monitoring skills.
