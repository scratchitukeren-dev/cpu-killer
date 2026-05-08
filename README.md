# ⚠️ CPU Killer (Fork Bomb Experiment)

A simple yet powerful "Fork Bomb" script written in Shell. This is created for educational purposes to understand how process management and resource exhaustion work in Linux/Unix environments.
---
> [!WARNING]
> **THIS SCRIPT IS HIGHLY DANGEROUS.**  
> Running this script will cause your system to freeze, lag, or crash (Kernel Panic) almost instantly.  
> **DO NOT run this on your physical host machine.**  
> If you want to test this, it is **STRONGLY RECOMMENDED** to use a Virtual Machine (e.g., **Oracle VirtualBox** or **VMware Workstation**). Using a VM ensures that only the guest OS crashes, keeping your main computer safe.
---
### 💻 The Logic
The script uses an infinite `while` loop combined with a background fork process to maximize impact:
``` bash
while true; do
 :|:&
done
```
---
### 🛠️ Why it's effective:
1. `while true;` - An infinite loop that never stops.
2. `:|:` - The function calls itself and pipes the output, doubling the process every cycle.
3. `&` - Forces the processes into the background, making it impossible to terminate with `Ctrl+C`.
4. `Instability` - On systems without `ulimit`, this will force a hard reboot.

---
*Created by scratchitukeren-dev for educational/experimental use only.*
