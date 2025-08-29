# Homelab GitOps with Flux

This repository manages my homelab Kubernetes cluster using **FluxCD** for GitOps automation.  
The repo is structured according to GitOps best practices, separating **applications**, **infrastructure**, and **cluster-specific configs**.

---

## 📂 Repository Structure
| Directory       | Purpose                                                                 |
|-----------------|-------------------------------------------------------------------------|
| `apps/`         | Application workloads (e.g., Postgres, monitoring, etc.)                |
| `infrastructure/` | Cluster-wide controllers, operators, and networking resources          |
| `clusters/`     | Cluster definitions and overlays (prod, dev, etc.)                      |

---

## 🚀 Applications Deployed
| Application        | Purpose                                      |
|--------------------|----------------------------------------------|
| Postgres           | Database service                             |
| cert-manager       | Automated TLS certificates                   |
| ingress-nginx      | Ingress controller for routing traffic       |
| prometheus-stack   | Monitoring and alerting                      |
| loki + grafana     | Log aggregation and visualization            |
| sealed-secrets     | Encrypted secrets management                 |
| external-dns       | Automated DNS record updates                 |
| *(extend as needed)* |                                              |

---

## 🏗️ Physical Infrastructure
| Component       | Details                                           |
|-----------------|---------------------------------------------------|
| **Rack Units**  | (e.g., 18U homelab rack)                         |
| **Networking**  | (e.g., Unifi switch + pfSense firewall)          |
| **Power**       | (e.g., dual UPS, PDU managed power strips)       |

---

## 🔧 Virtualization Layer (Proxmox VE)
| Attribute       | Details                                           |
|-----------------|---------------------------------------------------|
| **Hypervisor**  | Proxmox VE                                        |
| **Storage**     | (e.g., ZFS RAIDZ2, Ceph cluster, or SSD pool)     |
| **Backup**      | (e.g., Proxmox Backup Server, NAS replication)    |

---

## ☸️ Kubernetes Cluster Overview

### Control Plane
| Node          | vCPU | Memory | Disk  | OS                   |
|---------------|------|--------|-------|----------------------|
| prod-k8m-01   | XX   | XX GB  | XX GB | Ubuntu 22.04 LTS     |

### Worker Nodes
| Node          | vCPU | Memory | Disk  | OS                   |
|---------------|------|--------|-------|----------------------|
| prod-k8w-01   | XX   | XX GB  | XX GB | Ubuntu 22.04 LTS     |
| prod-k8w-02   | XX   | XX GB  | XX GB | Ubuntu 22.04 LTS     |
| prod-k8w-03   | XX   | XX GB  | XX GB | Ubuntu 22.04 LTS     |

---

## 🔒 GitOps Workflow
- **FluxCD** watches this repository.  
- Changes committed here are automatically reconciled into the cluster.  
- Separate overlays are used for **prod** vs. **dev** clusters, allowing safe testing before production rollout.  

---

## 🗺️ Roadmap
- [ ] Add staging cluster overlay  
- [ ] Expand monitoring stack (Thanos, Tempo)  
- [ ] Implement ArgoCD for progressive delivery  
- [ ] Explore multi-cluster networking with Cilium + BGP  

---

## 📜 License
This project is licensed under the MIT License – see the [LICENSE](./LICENSE) file for details.
