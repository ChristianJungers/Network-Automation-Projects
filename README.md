<img width="1499" height="901" alt="{08D79093-401D-41A8-B67B-3F7F98892AC6}" src="https://github.com/user-attachments/assets/5cb0d7c6-52c4-4106-8807-5514396af2af" />

# CML Network Automation Project 1

This project demonstrates a professional CI/CD approach to network infrastructure using Ansible and Cisco Modeling Labs (CML).

## Phase 0: Environment & Connectivity
- **Isolated Environment:** Implemented a Python virtual environment to manage dependencies and avoid system-wide conflicts.
- **Library Integration:** Configured the `virl2_client` and `cisco.cml` Ansible collection.
- **Interpreter Management:** Resolved Python interpreter discovery issues by explicitly mapping the Ansible controller to the virtual environment path.
- **API Verification:** Developed a "Smoke Test" playbook to verify authenticated connectivity to the CML REST API.

## Phase 1: Infrastructure as Code (IaC)
- **Declarative Deployment:** Pivoted from manual node creation to a declarative "Blueprint" approach using a `topology.yaml` file.
- **OOB Management Architecture:** Designed and implemented an **Out-of-Band (OOB) Management Network**.
  - Integrated an **External Connector (Bridge)** to link the virtual lab to the physical development environment.
  - Deployed an **Unmanaged Management Switch** to act as a central hub, overcoming CML's single-link limitation on the External Connector.
- **Schema Validation:** Troubleshot and resolved CML API validation errors regarding mandatory fields (versioning, interface types, and node-to-interface mapping).
- **Topology:** Deployed a 7 -node topology consisting of:
  - 3x Cisco IOSv Routers
  - 2x Cisco IOSvL2 Switches
  - 1x Unmanaged Management Switch
  - 1x External Connector

## Current Project State
The virtual hardware is fully deployed and wired according to the blueprint. The environment is ready for Phase 2: Configuration Management.