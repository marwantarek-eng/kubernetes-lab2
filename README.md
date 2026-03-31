# Kubernetes ITI Lab 46

This repository contains the completed tasks for the Kubernetes lab, demonstrating proficiency in creating namespaces, managing kubeconfig contexts, developing custom kubectl plugins, and configuring deployments with environment variables.

## 🛠️ Lab Objectives & Proof of Execution

### 1. Namespace Creation
**Task:** Create a new namespace called `iti-46`.
- A declarative approach was used via `namespace.yaml` to create the namespace.

<img width="752" height="169" alt="Screenshot 2026-03-31 154754" src="https://github.com/user-attachments/assets/15f35a12-daa0-4e90-85eb-20e65b36475c" />

---

### 2. Kubeconfig Context Management
**Task:** Edit the kubectl config file to add a new context (`iti-context`) that uses the default user with the new namespace.
- Successfully created and switched to `iti-context`.
- Verified the configuration using `kubectl config view`.

<img width="1415" height="492" alt="Screenshot 2026-03-31 155443" src="https://github.com/user-attachments/assets/86627500-19b3-4b30-baef-e5d7b3b7b1a5" />

---

### 3. Custom Kubectl Plugin
**Task:** Create a new kubectl plugin called `kubectl hostnames` to display the hostnames of all nodes on the cluster.
- Created a bash script parsing `kubectl get nodes` output.
- Made the script executable and placed it in the system's PATH.

<img width="614" height="199" alt="Screenshot 2026-03-31 221000" src="https://github.com/user-attachments/assets/5eb6e090-542c-4873-bced-7e3538e26085" />

---

### 4. Deployment & Environment Variables
**Task:** Create a deployment YAML file with 3 replicas of the `nginx:alpine` image. The pods must have an environment variable `FOO=ITI`.

**Deployment YAML Configuration:**
- Defined `apps/v1` Deployment.
- Configured correct `matchLabels` and `env` parameters.

<img width="708" height="667" alt="image" src="https://github.com/user-attachments/assets/179bba2a-09cb-424d-8a94-fc944ac8445e" />

**Deployment Execution & Verification:**
- Applied the deployment successfully.
- Verified the 3 running replicas within the `iti-46` namespace.
- Executed into one of the pods and ran `printenv FOO` to confirm the environment variable was injected correctly.
<img width="682" height="667" alt="Screenshot 2026-03-31 222636" src="https://github.com/user-attachments/assets/1b95f835-a096-4af2-a004-05114c520588" />

