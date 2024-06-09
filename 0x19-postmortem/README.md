# Postmortem: Server Outage on May 19, 2024

## Issue Summary

**Duration of the Outage**:  
Start Time: May 19, 2024, 03:00 UTC  
End Time: May 19, 2024, 05:30 UTC

**Impact**:  
The outage affected our main web application, causing complete downtime. Users experienced an inability to access the website, resulting in approximately 85% of our user base being affected.

**Root Cause**:  
The root cause of the outage was a misconfiguration in the load balancer that resulted in all incoming traffic being directed to a single server, which subsequently crashed due to overload.

## Timeline

- **03:00 UTC** - Issue detected via monitoring alert indicating a significant drop in successful HTTP requests.
- **03:05 UTC** - Engineers began investigating the alert, initially suspecting a server crash.
- **03:15 UTC** - Confirmed that a single server was receiving all traffic. Assumed an application-level issue.
- **03:30 UTC** - Misleading investigation paths included checking the application code for recent changes and inspecting the database for bottlenecks.
- **04:00 UTC** - Escalated to the network team to inspect the load balancer configuration.
- **04:15 UTC** - Network team identified the misconfiguration in the load balancer.
- **04:45 UTC** - Corrected the load balancer settings to distribute traffic evenly across all servers.
- **05:00 UTC** - Monitored server performance and ensured balanced traffic distribution.
- **05:30 UTC** - Issue resolved, normal service restored.

## Root Cause and Resolution

**Root Cause**:  
The load balancer was inadvertently misconfigured during a routine update. Instead of distributing traffic evenly across all servers, it directed all incoming requests to a single server. This server quickly became overwhelmed, leading to a crash and subsequent downtime.

**Resolution**:  
Once the issue was escalated to the network team, they identified the misconfiguration in the load balancer settings. The configuration was promptly corrected to ensure traffic was evenly distributed across all available servers. This involved updating the load balancer's settings and verifying the changes. The servers were then monitored to ensure they were handling the traffic appropriately.

## Corrective and Preventative Measures

**Improvements/Fixes**:
- **Load Balancer Configuration**: Implement strict change management procedures for load balancer configurations to prevent misconfigurations.
- **Enhanced Monitoring**: Add specific monitoring for load balancer traffic distribution to detect uneven traffic patterns early.
- **Automated Alerts**: Set up automated alerts for unusual traffic distribution across servers.
- **Training**: Provide additional training for engineers on the criticality of load balancer configurations and best practices.

**Tasks**:
1. Patch and update load balancer settings to include automated distribution checks.
2. Implement and configure monitoring tools to specifically track and alert on load balancer traffic patterns.
3. Review and update change management protocols to include a mandatory review for load balancer configuration changes.
4. Conduct training sessions for the engineering and network teams on load balancer management and best practices.
5. Perform regular audits of the load balancer settings and configurations to ensure compliance with best practices.

![Humorous Diagram](https://s3.amazonaws.com/intranet-projects-files/holbertonschool-sysadmin_devops/293/d42WuBh.png)

In summary, this outage highlighted the importance of stringent change management and the need for enhanced monitoring of critical infrastructure components. By implementing these corrective measures, we aim to prevent similar incidents in the future and ensure high availability for our users.
