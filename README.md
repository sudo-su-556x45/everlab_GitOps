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
|--------------------------|---------------------------------------------------|
| **Dell Poweredge R730**  | |
| **Dell Poweredge R730**  | |
| **Dell Poweredge R710**  | |
| **Cisco Catalyst**       | |

---

## 🔧 Virtualization Layer

###pve0 (Proxmox VE)
| VMID  | Hostname | OS |                                   |
|-------|---------------------------------------------------|
|       |                                        |
|       |    |
|       |    |

###pve1 (Proxmox VE)
| VMID  | Hostname | OS |                                   |
|-------|---------------------------------------------------|
|       |                                        |
|       |    |
|       |    |    

###pve2 (Proxmox VE)
| VMID  | Hostname | OS |                                   |
|-------|---------------------------------------------------|
|       |                                        |
|       |    |
|       |    |   
---

## ☸️ Kubernetes Cluster Overview

### Control Plane
| Node          | Host    | vCPU | Memory | Disk  | OS                   |
|---------------|---------|------|--------|-------|----------------------|
| prod-k8m-01   | pve0    | 1    | 2 GB  | 20 GB  | Debian 10            |

### Worker Nodes
| Node          | Host    | vCPU | Memory | Disk  | OS                   |
|---------------|---------|------|--------|-------|----------------------|
| prod-k8w-01   | pve0    | 4    | 16 GB  | 20 GB | Debian 10            |
| prod-k8w-02   | pve0    | 4    | 16 GB  | 20 GB | Debian 10            |
| prod-k8w-03   | pve0    | 4    | 16 GB  | 20 GB | Debian 10            |

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
