# **Endurance Testing Report**

## **🔹 General Information**
✅ **Test Type:** Endurance Testing  
✅ **Test Objective:** Checking server stability and performance under continuous load for an extended period.  
✅ **Tool Used:** JMeter 5.6.3 + Stepping Thread Group  
✅ **Tested Website:** fdout.pl  

---

## **🔹 Test Parameters**
📌 **Number of Users (Threads):** 20  
📌 **Ramp-up Time:** 5 minutes (gradual user increase over time)  
📌 **Test Duration:** 30 minutes  
📌 **User Increment Strategy:** 5 users every 5 minutes  
📌 **Test End Strategy:** Users gradually exiting every 2 minutes  

---

## **🔹 Test Execution Process**
1️⃣ The test starts with 0 active users.  
2️⃣ Every 5 minutes, 5 new users are added until reaching 20 concurrent users.  
3️⃣ All 20 users continuously interact with the website for 30 minutes.  
4️⃣ Gradual user exit: Every 2 minutes, 5 users stop interacting until all users finish.  

---

## **🔹 Test Results**
📌 **Full Report:** [index.html](./index.html)  
📊 **Performance Metrics:**
- ✅ **100% requests passed** (No failed requests detected)  
- ⏳ **Average response time:** 1985 ms  
- 🚀 **Peak response time:** 13,506 ms  
- 📈 **Throughput:** 0.99 transactions/sec  

---

## **🔹 Graphical Analysis**
📌 **Response Times Over Time:**
- **Initial response time:** 1071 ms – acceptable  
- **Peak response time:** 13,506 ms – critical latency detected  
- **Performance gradually declined under sustained load.**  

📌 **Hits Per Second:**
- Maximum sustained throughput: **1.2 hits/sec**  
- **Drop in requests towards the end** – potential resource limitations detected  

📌 **Response Time Percentiles:**
- 90th percentile response time: **2613 ms**  
- 99th percentile response time: **4997 ms**  
- **Indicates possible performance bottlenecks under continuous load.**  

---

## **🔹 Key Findings & Issues**
⚠️ **High response time fluctuations** (peak time reached 13.5 sec)  
⚠️ **Throughput is lower than expected** (0.99 TPS vs. 2+ TPS expected)  
⚠️ **Performance degradation over time** – signs of resource exhaustion  

---

## **🔹 Recommendations for Performance Improvement**
✅ **Optimize database queries** – possible slow SQL queries or indexing issues.  
✅ **Implement caching** – reduce redundant database requests.  
✅ **Scale server infrastructure** – ensure sufficient CPU & RAM.  
✅ **Check load balancing** – to prevent overload on certain components.  

---

## **🔹 Conclusion**
📌 **Endurance Testing identified critical performance issues.**  
📌 **Response time exceeded acceptable limits.**  
📌 **Throughput (TPS) was lower than expected, indicating inefficiency under sustained load.**  
📌 **Optimizations are required to improve server stability.**  

🔥 **Next Steps:**
1️⃣ **Discuss results with the team (DevOps, Backend).**  
2️⃣ **Prioritize performance optimizations.**  
3️⃣ **Re-run tests after improvements.**  


 


