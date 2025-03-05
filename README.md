# Endurance Testing Report

## Test Overview

🟢 **Test Type:** Endurance Testing  
🟢 **Objective:** Assess the stability and performance of the system over an extended period under sustained load.  
🟢 **Tool Used:** JMeter 5.6.3 + Stepping Thread Group  
🟢 **Target Website:** [fdout.pl](https://fdout.pl)  

---

## Test Parameters

🔹 **Number of Users (Threads):** 20  
🔹 **Ramp-up Time:** 5 sec (time taken to start the test)  
🔹 **Load Increase Strategy:** 10 threads added every 30 seconds  
🔹 **Test Duration:** 30 minutes  
🔹 **Cooldown Strategy:** Reducing 5 threads per second  

---

## How the Test Works

1️⃣ **Test starts with zero active users (0 threads).**  
2️⃣ **Every 30 seconds, 10 new users are added until reaching 20 concurrent users.**  
3️⃣ **Users continuously interact with the website for 30 minutes.**  
4️⃣ **Gradual cooldown, reducing 5 users per second until all users disconnect.**  

---

## Test Results

| Metric                      | Expected Value | Actual Value |
|-----------------------------|---------------|-------------|
| ✅ Average Response Time     | < 5 sec       | **32 sec ❌** |
| ✅ Maximum Response Time     | < 10 sec      | **83 sec ❌** |
| ✅ Throughput (Requests/sec) | > 10 req/sec  | **1.87 req/sec ❌** |

---

## Graphical Analysis

📊 **Response Times Over Time:** Response times increased with load. Initial response: **10,000ms (10 sec)** (acceptable), final response: **70,000ms (70 sec)** (critical).  
📊 **Hits Per Second:** Load peaked at **2.5 requests/sec**, later stabilizing at **1.8–2.3 requests/sec**. A sharp drop at the end suggests **server resource constraints or database bottlenecks**.  

---

## Key Issues Identified

⚠️ **Very High Average Response Time** (32 sec instead of <5 sec).  
⚠️ **Low Throughput (1.87 TPS)** – API processes too few requests.  
⚠️ **Response Time Increased 7x** compared to the initial state.  
⚠️ **Maximum Response Time Peaked at 83 sec**, which is extremely slow.  

---

## Recommendations for Improvement

✅ **Optimize Database Queries** – slow SQL queries or indexing issues might be causing delays.  
✅ **Use Caching** – caching requests can reduce database load.  
✅ **Scale Server Infrastructure** – the server might lack CPU/RAM resources.  
✅ **Load Balancing Check** – sudden performance drops may indicate **overloaded system components**.  

---

## Conclusion

✅ **Significant performance issues detected.**  
✅ **Response times exceed acceptable limits.**  
✅ **Throughput is critically low,** meaning the system struggles with load.  
✅ **Urgent optimization of server resources and database is required.**  

🔥 **Next Steps:**
1️⃣ **Discuss results with the team** (DevOps, Backend).  
2️⃣ **Prioritize performance improvements.**  
3️⃣ **Run another endurance test after optimization.**  

---
 


