# Day 2 – Performance Troubleshooting

## ❓ Question
**System is slow but CPU idle is high — what should you check first?**

### Options:
- Swap usage  
- I/O wait ✅  
- Thread count  
- SELinux status  

---

## ✅ Correct Answer: I/O wait

### 📌 Explanation

When a system is **slow but CPU idle is high**, it means:
- The CPU is **not the bottleneck**
- Processes are likely **waiting on something else**

The most common cause in this scenario is **high disk I/O wait**.

### 🔍 What is I/O wait?

- **I/O wait** is the percentage of time the CPU is idle **while waiting for disk I/O operations** to complete.
- Even though CPU appears "idle", it's actually **stalled waiting for storage** (disk, SSD, network storage).

### 🚨 Symptoms of High I/O Wait:
- Slow application response
- Delays in file access
- High load average but low CPU usage
- System feels "hung" or laggy

| Option         | Priority | Explanation                          |
| -------------- | -------- | ------------------------------------ |
| Swap usage     | Medium   | Affects performance when RAM is full |
| **I/O wait**   | ⭐ High   | Direct indicator of disk bottleneck |
| Thread count   | Low      | Impacts CPU usage, not idle state    |
| SELinux status | Low      | Rarely causes general slowdown       |


### 🛠️ How to Check:
```bash
top        # look at wa (I/O wait)
iostat -x 1
vmstat 1