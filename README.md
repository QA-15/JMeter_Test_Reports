# Endurance Testing Report

## 1️⃣ General Information

✅ **Test Type**: Endurance Testing  
✅ **Objective**: Evaluate the system's performance and stability over an extended period under continuous load.  
✅ **Tool Used**: JMeter 5.6.3 + Stepping Thread Group  
✅ **Target Website**: `fdout.pl`

## 2️⃣ Test Parameters

📌 **Number of Users (Threads)**: 50  
📌 **Ramp-up Time**: 10 minutes (gradual increase of users)  
📌 **Test Duration**: 60 minutes  
📌 **Sustained Load**: Users continuously interacting with the system for 60 minutes  
📌 **Gradual Exit Strategy**: Decreasing 5 users every minute until completion  

## 3️⃣ Test Execution Process

1️⃣ **Test starts with 0 active users.**  
2️⃣ **Every 1 minute, 5 new users are added until reaching 50 users.**  
3️⃣ **All users interact with the system continuously for 60 minutes.**  
4️⃣ **Gradual user exit – 5 users leave every minute until completion.**  

## 4️⃣ Test Results

📌 **Full Report**: [Endurance Test Report](https://qa-15.github.io/JMeter_Test_Reports/index.html)  

### Key Metrics
| Metric                     | Expected Value | Actual Value | Status |
|----------------------------|---------------|-------------|--------|
| ✅ Average Response Time  | < 3 sec       | 5.2 sec     | ❌ |
| ✅ Maximum Response Time  | < 8 sec       | 12.8 sec    | ❌ |
| ✅ Throughput (TPS)       | > 5 requests/sec | 3.2 requests/sec | ❌ |

## 5️⃣ Graphical Analysis

### Response Times Over Time  
📉 **Observation**: Response time increased steadily as test progressed.  
📍 **Initial response time**: 1500 ms (acceptable)  
📍 **Final response time**: 12,800 ms (critical degradation)  
🔴 **Conclusion**: Severe performance degradation after 30 minutes of sustained load.

### Hits Per Second (Requests Per Second)  
📍 **Initial peak**: 4.8 requests/sec  
📍 **Stabilization**: 3.2 requests/sec  
📍 **Drop near end of test**: Indicates possible database or server resource exhaustion.  

## 6️⃣ Key Findings & Issues

⚠️ **Severe performance degradation over time** – response time increased by 6x.  
⚠️ **Low Throughput (TPS)** – the system handled fewer requests than expected.  
⚠️ **Potential memory leaks or DB bottlenecks** – sudden spikes in response times.  

## 7️⃣ Recommendations for Performance Improvement

✔ **Optimize database queries** – slow SQL queries may be affecting performance.  
✔ **Implement caching mechanisms** – reduce repeated expensive queries.  
✔ **Scale infrastructure** – increase CPU/RAM if server resources are exhausted.  
✔ **Check load balancing** – verify if some components are overloaded.  

## ✅ Conclusion
📌 **Endurance testing revealed significant performance bottlenecks.**  
📌 **Response time increased beyond acceptable limits, indicating scalability issues.**  
📌 **Further optimization of server resources and database is required.**  

🔥 **Next Steps:**  
1️⃣ Discuss results with DevOps and Backend teams.  
2️⃣ Prioritize improvements in performance optimization.  
3️⃣ Re-run endurance testing after optimizations.  


