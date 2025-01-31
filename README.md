# 🏰 Kuberlandia Walls

**A Kubernetes adventure to master Network Policies in a medieval fantasy world**

Welcome to **Kuberlandia Walls**, an immersive learning experience where you will explore **Kubernetes Network Policies** through the **mystical realms of Kuberlandia**. Secure your kingdom, protect trade routes, and prevent spies from infiltrating your network!

## 🌍 The Kingdoms of Kuberlandia

Kuberlandia is divided into three great factions, each represented by a Kubernetes namespace:

1. **🏰 The Kingdom of Lumenia (`lumenia`)** – A prosperous city of merchants and scholars.
2. **🌑 The Citadel of Umbra (`umbra`)** – A dark fortress of spies and illusionists.
3. **🌲 The Wildlands (`wilderness`)** – A lawless land of wanderers and bandits.

Each kingdom has its own **inhabitants**, represented as Kubernetes Deployments with unique labels.

## 🚀 Getting Started

### 1️⃣ Install Kubernetes & kubectl
Ensure you have a running **Kubernetes cluster** and `kubectl` configured.

### 2️⃣ Clone the Repository
```sh
git clone https://github.com/its-me-mayday/kuberlandia-walls.git
cd kuberlandia-walls
```

### 3️⃣ Deploy the Kingdoms
```sh
kubectl apply -f once-upon-a-time/realms.yaml
kubectl apply -f once-upon-a-time/lumenia.yaml
kubectl apply -f once-upon-a-time/umbra.yaml
kubectl apply -f once-upon-a-time/wilderness.yaml
```

### 4️⃣ Test Network Connectivity
Before applying **Network Policies**, test if all pods can communicate freely:
```sh
kubectl get pods -A
kubectl exec -it <pod-name> -n lumenia -- curl <target-ip>:80
```

## 🏆 The Quests (Network Policies Challenges)

### 📜 **Mission 1: Defend Lumenia**
Block all incoming traffic to `lumenia` except from its own inhabitants.
```sh
kubectl apply -f network-policies/deny-external-traffic.yaml
```

### 🕵️ **Mission 2: Contain the Spies of Umbra**
Allow only `scholars` in Lumenia to receive messages from Umbra.
```sh
kubectl apply -f network-policies/allow-scholar-traffic.yaml
```

### 🏦 **Mission 3: Protect the Merchants' Trade Routes**
Allow only `merchants` to communicate with the Wildlands.
```sh
kubectl apply -f network-policies/merchants-can-contact-wilderness.yaml
```

### 🔮 **Bonus Mission: The Secret Portal**
Allow only port `8080` communication between Lumenia and Umbra.
```sh
kubectl apply -f network-policies/secret-portal.yaml
```

## 🏰 Contribute to Kuberlandia
Want to add new kingdoms, secret tunnels, or magical firewalls? Feel free to open a PR or suggest new challenges!

## 📜 License
MIT License. Free to explore, conquer, and secure your networks!

---
🛡️ **Fortify your Kubernetes clusters with the power of Kuberlandia Walls!** 🔥
