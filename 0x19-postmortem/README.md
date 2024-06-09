Postmortem Report: System Outage on E-commerce Platform
Issue Summary
Duration of the outage: June 8, 2024, from 14:00 to 16:30 UTC (2.5 hours)
Impact: The primary e-commerce service was down, preventing users from browsing products, adding items to their carts, and completing purchases. Approximately 75% of users were affected.
Root Cause: A misconfigured load balancer led to an unexpected traffic bottleneck, causing the web servers to become unresponsive.
Timeline
14:00 - Issue detected through an automated monitoring alert indicating increased error rates.
14:05 - Initial investigation began by the on-call engineer who confirmed the service was down.
14:15 - Assumption made that the issue was related to a recent database update. Database team notified.
14:30 - Database team confirmed no issues. Redirected focus to network infrastructure.
14:45 - Network team investigated load balancer configuration. Misleading logs suggested potential firewall issues.
15:00 - Executives and the customer support team informed of the ongoing outage and potential impact.
15:15 - Root cause identified: recent changes to load balancer configuration inadvertently set a limit on the maximum number of connections.
15:30 - Configuration corrected and load balancer restarted.
15:45 - Services began to recover gradually.
16:15 - Full functionality restored and verified through end-to-end tests.
16:30 - Post-incident review initiated.
Root Cause and Resolution
Root Cause: The primary cause of the outage was a misconfigured load balancer. A recent update to improve traffic distribution inadvertently introduced a configuration limit on the maximum number of simultaneous connections. This misconfiguration created a bottleneck that overwhelmed the web servers, leading to their unresponsiveness and preventing users from accessing the platform.
Resolution: Once the misconfiguration was identified, the load balancer settings were corrected to remove the imposed limit. The load balancer was then restarted to apply the new configuration. This immediately alleviated the bottleneck, allowing the web servers to resume normal operation. Full functionality was verified by running comprehensive end-to-end tests across the platform.
Corrective and Preventative Measures
Improvements:
Enhance the configuration change review process to ensure thorough validation and testing before deployment.
Implement additional monitoring to detect and alert on configuration anomalies in real-time.
Increase redundancy in load balancing to better handle unexpected traffic patterns and prevent single points of failure.
Tasks:
Patch load balancer settings: Review and update the load balancer configuration to prevent similar issues in the future.
Add monitoring: Implement monitoring on load balancer connection limits and traffic patterns to detect unusual behaviour early.
Conduct training: Provide training for the engineering team on best practices for load balancer configuration and management.
Review change management process: Strengthen the change management process to include more rigorous peer reviews and automated testing for critical infrastructure updates.
Implement redundancy: Deploy additional load balancers and set up automated failover mechanisms to ensure continuous service availability even during individual component failures.
By addressing these measures, we aim to prevent similar outages in the future and improve the overall resilience of our e-commerce platform.


