# Performance Analysis and Tuning of MinIO within a Kubernetes Environment

This repository contains the configuration and methodology for a performance analysis of MinIO object storage using the TPC-H benchmark executed by Apache Spark. The entire testbed is deployed on a local Kubernetes cluster and managed via a GitOps workflow with ArgoCD.

## Testbed Environment

The experiment is designed to be run on a local machine using Minikube. The following specifications were used to create the Kubernetes cluster for this analysis.

### Cluster Configuration

The cluster was provisioned with the following command:

```bash
minikube start --cpus=8 --memory=16gb --disk-size=100g
```

This creates a single-node cluster with the following key characteristics:

- **CPUs:** 8 cores
- **Memory:** 16 GB
- **Disk Size:** 100 GB

### Software Stack & Versions

Reproducibility is critical. The foundational components of this analysis are pinned to the following software versions:

| Component  | Version   | Notes                              |
| ---------- | --------- | ---------------------------------- |
| Minikube   | `v1.36.0` | Local Kubernetes provider          |
| Kubernetes | `v1.33.1` | Version provisioned by Minikube    |
| Docker     | `28.1.1`  | Container runtime used by Minikube |
| ArgoCD     | `v3.1.7`  | GitOps controller                  |
