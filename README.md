
# **Endurance Testing Report**
## **Project:** Performance Testing of Web Pages  
**Test Type:** Endurance Testing  
**Test Tool:** JMeter  
**Test Date:** March 5, 2025  
**Test Duration:** 30 minutes  
**Tested Pages:**  
- Mane_Page  
- Beauty_1_Page  
- Expert_Page  

---

## **1. Test Configuration**
- **Test Plan:** Stepping Thread Group  
- **Concurrent Users:** 2  
- **Execution Time:** 30 minutes  
- **Metrics Captured:**  
  - Response Time (Average, Min, Max)  
  - Throughput (Transactions/sec)  
  - APDEX (Application Performance Index)  
  - Hits Per Second  
  - Percentiles of Response Time  

---

## **2. Summary of Test Results**
### **2.1. General Information**
| Parameter  | Value |
|------------|----------------------|
| **Source File** | results.jtl |
| **Start Time** | 3/5/25, 8:08 PM |
| **End Time** | 3/5/25, 8:38 PM |

- The endurance test ran successfully for 30 minutes.  
- No errors (0.00% error rate) were observed.  
- Response times and throughput were captured for analysis.  

---

## **3. Key Performance Metrics**
### **3.1. APDEX (Application Performance Index)**
| Page | APDEX Score | T (Toleration Threshold) | F (Frustration Threshold) |
|------|------------|---------------------------|---------------------------|
| Mane_Page | 0.010 | 500ms | 1 sec 500ms |
| Beauty_1_Page | 0.034 | 500ms | 1 sec 500ms |
| Expert_Page | 0.246 | 500ms | 1 sec 500ms |
| **Total (Overall)** | **0.097** | **500ms** | **1 sec 500ms** |

📌 *APDEX score below 0.5 indicates poor performance. All tested pages have a low APDEX score, suggesting performance issues.*

---

### **3.2. Response Time Analysis**
| Page | Samples | Average (ms) | Min (ms) | Max (ms) | 90th pct (ms) | 99th pct (ms) |
|------|---------|-------------|---------|---------|-------------|-------------|
| **Total** | 1795 | 1985.78 | 1071 | 13506 | 2613.60 | 4997.80 |
| Beauty_1_Page | 598 | 2147.06 | 1268 | 13506 | 2713.00 | 4779.64 |
| Expert_Page | 598 | 1621.55 | 1071 | 4995 | 2358.15 | 3393.25 |
| Mane_Page | 599 | 2188.40 | 1349 | 12961 | 2896.00 | 5342.00 |

📌 *Significant variation in response time observed, with high maximum response times (up to 13.5 sec). Expert_Page had the best performance with the lowest average response time.*

---

### **3.3. Response Time Over Time**
- **Observation:**  
  - Response times were inconsistent, with frequent spikes.  
  - Mane_Page and Beauty_1_Page had the highest latency spikes (~4000ms).  
  - Expert_Page maintained relatively stable response times.  
  - High latency periods indicate possible backend bottlenecks.

📌 *Recommendation:* Optimize database queries, caching, and server load balancing to mitigate response time fluctuations.

---

### **3.4. Hits Per Second**
- **Observation:**  
  - Initial ramp-up period showed a gradual increase in requests.  
  - The system maintained a stable hit rate of ~1 request/sec.  
  - There was a temporary drop at 20:14, possibly due to resource saturation.

📌 *Recommendation:* Ensure server scaling mechanisms are in place to handle sustained loads.

---

### **3.5. Response Time Percentiles**
- The **99th percentile response time** exceeded **10 sec**, which is unacceptable for a good user experience.  
- The **90th percentile response time** remained between **2500ms - 3500ms**, which is considered slow.

📌 *Recommendation:*  
- Optimize API responses and database queries.  
- Investigate caching mechanisms to improve response times.

---

## **4. Conclusion & Next Steps**
### **4.1. Key Findings**
✅ **Positive Aspects:**  
- No errors detected during the test (0% error rate).  
- System handled sustained load without failures.

⚠️ **Areas for Improvement:**  
- High response times across all pages.  
- Large variance in response time with latency spikes.  
- APDEX score is low, indicating poor user experience.

### **4.2. Action Items**
- **Backend Optimization:** Investigate slow queries and API response times.  
- **Load Balancing:** Implement auto-scaling and caching strategies.  
- **Further Testing:** Conduct stress and scalability tests to evaluate system behavior under increased load.  

---

## **5. Report Hosting & GitHub Deployment**
- The test results and report were uploaded to GitHub at:  
  🔗 **[GitHub Repository](https://github.com/QA-15/JMeter_Test_Reports)**
- The **performance report** is accessible via GitHub Pages:  
  🔗 **[Live Report](https://qa-15.github.io/JMeter_Test_Reports/)**  

---

**End of Report**  
📌 *Prepared by Halyna (QA-15)
