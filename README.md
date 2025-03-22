[README.pdf](https://github.com/user-attachments/files/19393545/README.pdf)

---

## **FAME (Fair Agent Matching Engine) – Project Summary**

### **Overview**  
FAME is a recommendation system designed to optimize the matching process between insurance clients and financial advisors. It aims to improve client satisfaction, reduce unethical sales practices, and ensure equitable access to services for all economic and demographic groups.

---

### **Objectives**  
- Improve client-agent compatibility using historical and demographic data  
- Minimize unethical upselling by incorporating agent behavior into scoring  
- Promote fairness by supporting new or underrepresented agents  
- Ensure equitable advisor access for clients across economic backgrounds

---

### **Dataset Description**  
The model uses structured data from three sources:
- **Agent Information**: demographics, experience, performance metrics  
- **Client Information**: age, household size, economic status  
- **Policy Information**: product type, premium amounts, policy outcomes (active, cancelled, lapsed)

---

### **Methodology**  
#### 1. Feature-Weighted Euclidean Similarity (FWES)  
A content-based algorithm that calculates similarity between a client’s profile and agent profiles, using weighted features. For example, economic status receives a higher weight (40%) compared to other attributes. Race is excluded to avoid bias. Top 20 agents with the highest similarity scores are shortlisted.

#### 2. Comprehensive Agent Scoring Model  
Builds on FWES by incorporating:
- **Compatibility Score** (weighted ×12)  
- **Fairness Score** (weighted ×4)  
- **Cancellation Rate Penalty** (weighted ×−5)  
The model ranks the top 5 agents per client based on this combined score.

---

### **Results and Performance**  
- Achieved a precision rate of 10%, significantly outperforming the 0.005% baseline of random matching across 20,000 agents  
- Prevented excessive workload on top agents by providing multiple matching options per client  
- Demonstrated a measurable relationship between cancellation rate and total score (slope = −1.225)

---

### **Strengths**  
- Capable of providing meaningful recommendations even for new clients  
- Promotes workload distribution and fairness across the advisor pool  
- Designed with ethical considerations, including exclusion of race and inclusion of new agents

---

### **Limitations**  
- Assumes that historical matches reflect ideal outcomes  
- May overlook qualitative factors such as communication skills or advisor specialization  
- Data sparsity may reduce accuracy for agents with limited historical records

---

### **Proposed Future Enhancements**  
- **Adaptive Weighting**: Introduce dynamic weighting based on client engagement history or recent financial progress  
- **Fairness-Aware Machine Learning**: Incorporate real-time fairness tracking and bias correction algorithms  
- **Client Feedback Integration**: Develop mechanisms for clients to rate advisors, refining recommendations over time

---

### **Fairness Checker (Prototype in Development)**  
Includes two main components:
- **Agent Stability Score**: Evaluates advisor reliability through policy history  
- **Economic Matching Score**: Balances assignment of advisors across income levels to avoid concentration of top advisors among high-income clients

These components help evaluate the ethical soundness of advisor-client pairings and improve model transparency and equity.

---
Co-Author:
Zhang Zizhong, Yao William, Wu Chia-Tung, Chen Ping

