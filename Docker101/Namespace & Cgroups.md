# Docker Containerization: Namespaces & cgroups

## 1. Namespaces → Isolation
**Purpose:** Provide isolated views of system resources to each container.  

**Types:**
- **PID** → separate process trees (each container thinks it’s PID 1).  
- **NET** → independent network stack (IP, interfaces, routes).  
- **MNT** → isolated filesystem mounts.  
- **UTS** → unique hostname/domain.  
- **USER** → isolated user & group IDs.  
- **IPC** → separate shared memory & message queues.  

**Effect:** Each container feels like it’s running on its own machine.  

---

## 2. cgroups (Control Groups) → Resource Control
**Purpose:** Limit and monitor container resource usage.  

**Controls:**
- **CPU time** → shares/quotas per container.  
- **Memory usage** → hard/soft limits.  
- **Block I/O** → disk throughput per container.  
- **Network bandwidth** → controlled via traffic shaping (tc + cgroups).  

**Effect:** Prevents one container from hogging system resources.  

---

## 3. Platform Differences in Containerization

| Platform  | How Docker Works Under the Hood                                                                                   |
|-----------|-------------------------------------------------------------------------------------------------------------------|
| **Linux** | ✅ Native: Uses **Linux kernel features** directly → `namespaces + cgroups + OverlayFS`. Most efficient execution. |
| **Windows** | ⚡ Two modes:<br>1. **Windows Containers** → Uses Windows kernel isolation (job objects, siloed processes, Hyper-V isolation).<br>2. **Linux Containers on Windows (LCOW)** → Runs a lightweight **Linux VM via Hyper-V** → provides namespaces + cgroups inside. |
| **macOS** | 🍏 No namespaces/cgroups in Darwin kernel. Docker Desktop runs a **Linux VM** (HyperKit/QEMU/Apple HVF) → all containers run inside that VM. |

---

## 🔑 Summary
- **Namespaces = Isolation** (who sees what).  
- **cgroups = Resource Control** (how much they get).  
- **Linux** → native containerization.  
- **Windows** → either Windows kernel isolation or Linux VM.  
- **macOS** → always a Linux VM under the hood.
