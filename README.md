# CML Network Automation Project 1

This project demonstrates a professional CI/CD approach to network infrastructure using Ansible and Cisco Modeling Labs (CML).

## Phase 0: Environment & Connectivity
- **Isolated Environment:** Implemented a Python virtual environment to manage dependencies and avoid system-wide conflicts.
- **Library Integration:** Configured the `virl2_client` and `cisco.cml` Ansible collection.
- **Interpreter Management:** Resolved Python interpreter discovery issues by explicitly mapping the Ansible controller to the virtual environment path.
- **API Verification:** Developed a "Smoke Test" playbook to verify authenticated connectivity to the CML REST API.

## Phase 1: Infrastructure as Code (IaC)
- **Declarative Deployment:** Pivoted from manual node creation to a declarative "Blueprint" approach using a `topology.yaml` file.
- **Schema Validation:** Troubleshot and resolved CML API validation errors regarding mandatory fields (versioning, interface types, and node-to-interface mapping).
- **Topology:** Deployed a 5-node topology consisting of:
  - 3x Cisco IOSv Routers
  - 2x Cisco IOSvL2 Switches
- **Idempotency:** The deployment playbook ensures the lab exists and is in the correct state without duplicating resources on subsequent runs.

## Current Project State
The virtual hardware is fully deployed and wired according to the blueprint. The environment is ready for Phase 2: Configuration Management.