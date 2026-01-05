# ☸️ K3s Installation with Ansible

![Kubernetes](https://img.shields.io/badge/Kubernetes-K3s-326ce5?logo=kubernetes&logoColor=white)
![Ansible](https://img.shields.io/badge/Ansible-Automation-EE0000?logo=ansible&logoColor=white)
![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)
![Status](https://img.shields.io/badge/Status-Active-success)

---

## 📖 Overview

This project installs **:contentReference[oaicite:0]{index=0}**, a lightweight Kubernetes distribution, using **:contentReference[oaicite:1]{index=1}**.

The installation is fully automated and managed through the Ansible collection:


It is designed to be:
- ✅ Simple
- ✅ Repeatable
- ✅ Idempotent
- ✅ Suitable for homelabs and small clusters

---

## ✨ Features

- 🚀 Automated K3s server & agent installation
- 🔐 Secure token-based node joining
- 🧩 Supports multi-node clusters
- 🔁 Idempotent Ansible roles
- 🛠 Minimal manual configuration

---

## 📦 Collection Information

| Item | Value |
|-----|------|
| **Collection Name** | `lxhome.kubernetes.k3s` |
| **Technology** | Ansible |
| **Kubernetes Distribution** | K3s |
| **Target OS** | Linux (systemd-based) |

---

## 📁 Example Inventory

```ini
[k3s_server]
k3smaster ansible_host=192.168.8.228

[k3s_agents]
k3snode1 ansible_host=192.168.8.229
k3snode2 ansible_host=192.168.8.230
```


# ▶️ ------Usage (Step 1)-------
Install the collection:
***This installs the `collection` in your system***
```shell
ansible-galaxy collection install lxhome.kubernetes.k3s
```
# :computer: -------Run the playbook: (Step 2)-------
***This runs the `playbook`***
```shell
ansible-playbook -i inventory.ini site.yml
```

## 🧠 How It Works
- Installs K3s server on the control node
- Retrieves the cluster token securely
- Joins agent nodes to the cluster
- Configures kubeconfig access on the server

## 🔒 Security Notes
- Kubeconfig is generated only on the server node
- Agents do not expose the Kubernetes API
- API access is controlled via tokens and certificates

## 📌 Requirements
- Ansible ≥ 2.14
- SSH access to all nodes
- Linux with systemd
- Internet access (or mirrored K3s binaries)

## 📜 License
Licensed under the Apache License 2.0.
See the **`LICENSE`** file for details.

## 🤝 Contributing
Contributions, issues, and feature requests are welcome.

## ⭐ Acknowledgements
- Rancher Labs for K3s
- Red Hat for Ansible