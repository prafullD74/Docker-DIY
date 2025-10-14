Below is a basic outline for a Root Cause Analysis (RCA) document for a server failing due to high CPU and memory usage. Since you requested a "basic word file," I’ll provide the content in a format suitable for copying into a Microsoft Word document, structured with headings and sections typically found in an RCA report. You can paste this into Word, format it (e.g., add headers, footers, or company logos), and adjust as needed.

---

**[Your Company Name]**
**Root Cause Analysis (RCA) Report**

**Document Title:** RCA - Server Failure Due to High CPU and Memory Usage  
**Server Name:** [e.g., prod-emailserver04]  
**Date of Incident:** [e.g., August 13, 2025]  
**Date of Analysis:** August 14, 2025  
**Prepared By:** [Your Name/Team Name]  
**Reviewed By:** [Reviewer Name, if applicable]  

---

### 1. Incident Overview
- **Date and Time of Failure:** [e.g., August 13, 2025, 10:00 AM IST]  
- **Affected System:** [e.g., prod-emailserver04, an EC2 instance hosting email services]  
- **Impact:** The server became unresponsive, leading to email service downtime affecting [number] users for [duration, e.g., 2 hours].  
- **Initial Symptoms:** High CPU utilization (e.g., 95-100%) and memory usage (e.g., 90-95%) observed via monitoring tools.  

---

### 2. Timeline of Events
- **[Time]:** Incident detected via [monitoring tool, e.g., CloudWatch] showing CPU at 95% and memory at 90%.  
- **[Time]:** Alerts triggered and support team notified.  
- **[Time]:** Manual investigation began, including checking logs and processes.  
- **[Time]:** Server restarted to restore service.  
- **[Time]:** Service restored, but root cause analysis initiated.  

---

### 3. Root Cause Analysis
#### 3.1 Data Collection
- **Monitoring Data:** CPU usage peaked at 98% and memory at 93% (sourced from [tool, e.g., CloudWatch metrics]).  
- **Log Analysis:** System logs (e.g., `/var/log/messages`) showed multiple processes consuming excessive resources.  
- **Process Monitoring:** `top` or `htop` identified [e.g., a mail server process or script] as the primary resource hog.  

#### 3.2 Identified Root Cause
- **Primary Cause:** High CPU and memory usage caused by [e.g., a runaway process, such as an email queue processor or a misconfigured cron job running rsync].  
- **Contributing Factors:**  
  - [e.g., Insufficient instance size (e.g., t3.micro) for the workload.]  
  - [e.g., Lack of resource limits on the process.]  
  - [e.g., Sudden spike in email traffic or data sync operations.]  

#### 3.3 Evidence
- Screenshots/Logs: [Attach or reference CPU/memory graphs, process list from `top`, or log excerpts.]  
- Metrics: [e.g., Average CPU usage over 24 hours exceeded 80% baseline.]  

---

### 4. Impact Assessment
- **Service Downtime:** [e.g., 2 hours]  
- **User Impact:** [e.g., 500 users unable to send/receive emails.]  
- **Business Impact:** [e.g., Delayed communications, potential revenue loss of $X.]  

---

### 5. Corrective Actions
- **Immediate Actions Taken:**  
  - Restarted the server to restore service.  
  - Terminated the offending process (e.g., killed the script/process ID).  
- **Short-Term Fixes:**  
  - Increased instance type to [e.g., t3.large] to handle higher load.  
  - Set resource limits using [e.g., `ulimit` or cgroup] on critical processes.  
- **Long-Term Recommendations:**  
  - Optimize the workload (e.g., schedule rsync during off-peak hours).  
  - Implement auto-scaling or load balancing for email services.  
  - Regular monitoring and alerting for CPU/memory thresholds.  

---

### 6. Preventive Measures
- Configure CloudWatch alarms to notify at 70% CPU/memory usage.  
- Conduct periodic performance testing to identify bottlenecks.  
- Document and review process configurations (e.g., cron jobs) monthly.  

---

### 7. Conclusion
The server failure on [date] was due to high CPU and memory usage caused by [root cause]. Immediate actions restored service, and the recommended fixes aim to prevent recurrence. Further review is scheduled for [date] to ensure stability.

---

### 8. Appendices
- **Appendix A:** Monitoring Screenshots  
- **Appendix B:** Log Excerpts  
- **Appendix C:** Process List Output  

---

### Notes for Customization
- Replace placeholders (e.g., [e.g., prod-emailserver04], [date]) with actual details.
- Add specific data from your server (e.g., instance type, OS, logs) for accuracy.
- Format in Word with headings (e.g., Heading 1 for sections, Heading 2 for subsections) and tables if needed.

This template provides a structured RCA that you can expand based on your server’s specifics. Let me know if you need help with logs or further details!
