### **Endurance Testing Report**

---

## **1️⃣ General Information**

✅ **Test Type:** Endurance Testing  
✅ **Test Objective:** Evaluate system stability and performance over a prolonged period under a constant load.  
✅ **Tool Used:** JMeter 5.6.3 + Stepping Thread Group  
✅ **Website:** `fdout.pl`

---

## **2️⃣ Test Parameters**

📌 **Number of Users (Threads):** 20  
📌 **Ramp-up Time:** 5 sec  
📌 **Load Increase:** 10 threads every 30 seconds  
📌 **Sustained Load Duration:** 30 minutes  
📌 **Load Reduction Strategy:** 5 threads decrease every second  

---

## **3️⃣ How the Load Was Applied?**

1️⃣ The test starts with 0 active users.  
2️⃣ Every 30 seconds, 10 new users are added until 20 concurrent users are reached.  
3️⃣ The 20 users interact with the website for 30 minutes.  
4️⃣ The test gradually finishes by removing 5 users per second.  

---

## **4️⃣ Test Results**

📌 **Summary Report:**  

- **Total Requests:** `1795`  
- **Failures:** `0 (0.00%)`  
- **Average Response Time:** `1985 ms`  
- **Max Response Time:** `13506 ms`  
- **Median Response Time:** `1857 ms`  
- **95th Percentile:** `2968 ms`  
- **99th Percentile:** `4997 ms`  
- **Throughput:** `0.99 transactions/sec`  
- **Network Speed:** `1351 KB/sec`  

📌 **Requests Summary:**  
✅ `100%` of requests **passed**, no failed requests detected.

---

## **5️⃣ Graphical Analysis**

### **Response Times Over Time**
📌 Response times fluctuated but remained relatively stable.  
📌 Peak response time reached **~4000 ms**, with **median ~1857 ms**.  
📌 Minor spikes indicate potential performance bottlenecks.

### **Hits Per Second**
📌 The request rate stabilized at **1.0-1.2 hits/sec**.  
📌 Some fluctuations observed, possibly due to resource exhaustion.

### **Response Time Percentiles**
📌 **95% of requests** were processed in **less than 2968 ms**.  
📌 **99% of requests** were completed within **4997 ms**, but extreme cases reached **13506 ms**.  

---

## **6️⃣ Key Findings & Issues**

⚠️ **Average Response Time is high (1985 ms), ideally should be < 1000 ms**.  
⚠️ **Throughput is low (~1 TPS), indicating the system is processing fewer requests than expected.**  
⚠️ **Max response time reached 13506 ms, indicating possible slow queries or resource exhaustion.**  
⚠️ **Some response spikes suggest performance inconsistencies under prolonged load.**  

---

## **7️⃣ Recommendations for Performance Improvement**

✔️ **Optimize Database Queries** - Investigate slow SQL queries or indexing issues.  
✔️ **Implement Caching** - Reduce repeated database queries by caching frequently accessed data.  
✔️ **Increase Server Resources** - Scale up CPU/RAM if necessary.  
✔️ **Load Balancing** - Distribute traffic across multiple servers if applicable.  

---

## **Conclusion**

📌 The endurance test revealed **stability**, as no failures were detected. However, **performance degradation** was observed over time. Response times increased significantly, indicating potential resource limitations or inefficient database queries.  

🔥 **Next Steps:**  
1️⃣ Discuss findings with the development team (Backend, DevOps).  
2️⃣ Prioritize performance improvements.  
3️⃣ Rerun the endurance test after optimizations.  

📌 Full Report: Endurance Test Report
https://qa-15.github.io/JMeter_Test_Reports/



 


